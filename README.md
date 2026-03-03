# 🎉 FestiveLink

> **AI-Powered Occasion & Festival Greeting Link Generator**  
> _Send personalized, themed greeting pages via a unique shareable link — powered by Gemini AI._

![Version](https://img.shields.io/badge/version-2.0.0-blue)
![Status](https://img.shields.io/badge/status-active-brightgreen)
![Tech](https://img.shields.io/badge/stack-HTML%20%7C%20CSS%20%7C%20JavaScript-yellow)
![AI](https://img.shields.io/badge/AI-Gemini%202.0%20Flash-purple)
![License](https://img.shields.io/badge/license-MIT-green)
![Serverless](https://img.shields.io/badge/architecture-serverless-brightgreen)

---

## 🌟 What is FestiveLink?

FestiveLink is a **fully serverless**, browser-based web application that lets anyone create a personalized greeting page and share it as a unique link — no coding, no apps, no sign-up required.

**v2.0** brings **Gemini AI** directly into the browser — no backend needed. Your API key stays local.

We support **15 distinct occasions + unlimited custom occasions**:
- **9 Festivals**: Holi, Diwali, Eid, Ramzan, Christmas, New Year, Navratri, Onam, Lohri.
- **6 Life Events**: Birthday, Wedding, Anniversary, Graduation, Baby Shower, Thank You.

---

## 🤖 AI Features (Gemini-Powered)

| Feature | What it does |
|---|---|
| ✨ **AI Message Generator** | Generates a warm, personalized greeting message based on occasion, sender & receiver names |
| 🎭 **Message Tone Changer** | Rewrites existing message in Funny 😄, Heartfelt 💖, or Formal 🎩 tone |
| 🎨 **Custom Theme Suggester** | Suggests culturally-appropriate color palettes for the occasion — applied to the live greeting page |

> **Privacy**: Your Gemini API key is stored only in `sessionStorage` — it never leaves your browser.

---

## 🔄 How It Works

### Sender Side (Creator)
1. Open FestiveLink homepage (`index.html`)
2. Enter your Gemini API key (get one free at [aistudio.google.com](https://aistudio.google.com/app/apikey))
3. Select an Occasion.
4. Optionally: click **🎨 AI Theme** to get an AI-suggested color theme.
5. Enter Sender Name, Receiver Name.
6. Click **✨ Generate with AI** to get a personalized message — or type your own.
7. Optionally change the tone: Funny / Heartfelt / Formal.
8. Click "Generate Link" → Share via WhatsApp or copy to clipboard.

### Receiver Side (Viewer)
1. Receiver opens the shared link.
2. Full-screen themed page loads instantly (with AI theme if suggested).
3. Animated popup appears with receiver's name and personalized message.
4. Particle animations play in the background.

---

## 🔐 Under the Hood (URL Encoding)

```
User Input + AI-generated content
        ↓
JSON Object { sender, receiver, message, festival, aiTheme? }
        ↓
encodeURIComponent() → btoa() → URL Parameter
        ↓
view.html?d={base64}
        ↓
atob() → decodeURIComponent() → JSON.parse()
        ↓
Theme Applied (static CSS class + optional AI color override) + Popup Rendered
```

> No server. No database. No persistent storage of personal data.

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 |
| Styling | CSS3 + Animations |
| Logic | JavaScript ES6+ (Canvas, Base64, fetch) |
| AI | Gemini 2.0 Flash REST API (client-side) |
| Sharing | WhatsApp Web API (`wa.me`) |
| Fonts | Google Fonts (Poppins, Baloo 2) |

---

## 🚀 Getting Started

No installation needed. Just open in a browser.

```bash
git clone https://github.com/ayankhan964825-lab/project-2-.git
cd project-2-
```

Use VS Code Live Server:
`Right-click index.html → "Open with Live Server"`

Then get a **free Gemini API key** at: https://aistudio.google.com/app/apikey

---

## 📄 Documentation
- `PRD.md` — Product Requirements Document
- `TRD.md` — Technical Requirements Document
- `DESIGN_SCHEMA.md` — Design System & Theme config
- `SYSTEM_ARCHITECTURE.md` — Architecture & Data Flow

## 📃 License
MIT License — free to use, modify, and distribute.
