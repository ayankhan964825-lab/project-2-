# FestiveLink — System Architecture (v2.0)

## Overview

FestiveLink v2.0 is a **hybrid serverless** web application. The core greeting-link flow remains 100% serverless (no backend), while Gemini AI features run as direct browser-to-API calls using the user's API key.

---

## Architecture Diagram

```
┌────────────────────────────────────────────────────────────────┐
│                        USER'S BROWSER                          │
│                                                                │
│  ┌─────────────────────────────────────────────────────────┐  │
│  │                      index.html                         │  │
│  │                                                         │  │
│  │   [API Key Banner] ──── sessionStorage ─────────────┐  │  │
│  │          │                                           │  │  │
│  │   [Occasion Selector]                                │  │  │
│  │          │                                           ▼  │  │
│  │   [AI Theme Suggester] ─── callGemini() ────► Gemini   │  │
│  │          │                                    REST API  │  │
│  │   [Name Inputs]              ▲                    │     │  │
│  │          │                   │                    │     │  │
│  │   [AI Message Generator] ───► callGemini()◄───────┘     │  │
│  │          │                                              │  │
│  │   [Tone Changer (F/H/F)] ──► callGemini()              │  │
│  │          │                                              │  │
│  │   [Generate Link Button]                               │  │
│  │          │                                              │  │
│  │          ▼                                              │  │
│  │   btoa(encodeURIComponent(JSON.stringify({              │  │
│  │       sender, receiver, message, festival,              │  │
│  │       aiTheme? ← from Theme Suggester                  │  │
│  │   })))                                                  │  │
│  │          │                                              │  │
│  │          ▼                                              │  │
│  │   view.html?d={base64_encoded_data}                    │  │
│  └─────────────────────────────────────────────────────────┘  │
│                                                                │
│  ┌─────────────────────────────────────────────────────────┐  │
│  │                       view.html                         │  │
│  │                                                         │  │
│  │   URL param ?d= → atob() → JSON.parse()                │  │
│  │          │                                              │  │
│  │          ├── Apply festival CSS class (static theme)    │  │
│  │          ├── If aiTheme present → inject <style> tag    │  │
│  │          ├── Render greeting popup (name + message)     │  │
│  │          └── Run canvas particle animation              │  │
│  └─────────────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────────────┘
                          │
                          ▼
         Gemini 2.0 Flash REST API
         (api.generativelanguage.googleapis.com)
         • Called directly from browser
         • User's own API key (sessionStorage only)
         • Never hits any FestiveLink server
```

---

## Data Flow

### Greeting Data Payload (URL-encoded)
```json
{
  "sender":     "Priya",
  "receiver":   "Rahul",
  "message":    "Wishing you a colorful Holi...",
  "festival":   "holi",
  "version":    "2.0",
  "customName": "(only if festival = 'custom')",
  "aiTheme": {
    "bg":        "#2D0A6E",
    "secondary": "#4A1580",
    "accent":    "#FF6B35",
    "name":      "Festive Violet"
  }
}
```

### AI Call Pattern
All three AI features use the same shared `callGemini(prompt)` helper:
- **Endpoint**: `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent`
- **Auth**: User's own key via query param `?key=...`
- **Request**: `POST` with `{ contents: [{ parts: [{ text: prompt }] }] }`

---

## Key Design Decisions

| Decision | Rationale |
|---|---|
| API key in `sessionStorage` | Never persisted on disk; cleared on browser close; never sent to any FestiveLink server |
| Direct browser → Gemini API | No backend needed; key doesn't pass through any proxy |
| AI theme encoded in URL | view.html needs zero API calls; works offline after link is generated |
| Fallback to static themes | If no aiTheme, existing festival CSS classes apply — backwards compatible |
| Shared `callGemini()` helper | DRY, single error-handling path for all AI features |
