# 🎉 FestiveLink

> **Occasion & Festival Greeting Link Generator Platform**  
> _Send personalized, themed greeting pages via a unique shareable link — no app, no backend, just pure joy._

![Version](https://img.shields.io/badge/version-1.1.0-blue)
![Status](https://img.shields.io/badge/status-pre--development-orange)
![Tech](https://img.shields.io/badge/stack-HTML%20%7C%20CSS%20%7C%20JavaScript-yellow)
![License](https://img.shields.io/badge/license-MIT-green)
![Serverless](https://img.shields.io/badge/architecture-serverless-brightgreen)

---

## 🌟 What is FestiveLink?

FestiveLink is a **fully serverless**, browser-based web application that lets anyone create a personalized greeting page and share it as a unique link — no coding, no apps, no sign-up required.

We support 15 distinct occasions:
- **9 Festivals**: Holi, Diwali, Eid, Ramzan, Christmas, New Year, Navratri, Onam, Lohri.
- **6 Life Events**: Birthday, Wedding, Anniversary, Graduation, Baby Shower, Thank You.

## 🔄 How It Works

### Sender Side (Creator)
1. Open FestiveLink homepage (`index.html`)
2. Select an Occasion.
3. Enter Sender Name, Receiver Name, and Personal Message.
4. Click "Generate Link".
5. Share via WhatsApp or copy to clipboard.

### Receiver Side (Viewer)
1. Receiver opens the shared link.
2. Full-screen themed page loads instantly.
3. Animated popup appears with receiver's name.
4. Personal message and sender name are displayed.
5. Particle animations play in the background.

## 🔐 Under the Hood (URL Encoding)
```
Sender Input → JSON Object → encodeURIComponent() → btoa() → URL Parameter
                                                                    |
                                                           view.html?d={base64}
                                                                    |
                                              atob() → decodeURIComponent() → JSON.parse()
                                                                    |
                                                    Theme Applied + Popup Rendered
```
> No server. No database. No API call. Everything lives in the URL.

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Structure | HTML5 |
| Styling | CSS3 + Animations |
| Logic | JavaScript ES6+ (Canvas, Base64) |
| Sharing | WhatsApp Web API (`wa.me`) |
| Fonts | Google Fonts (Poppins, Baloo 2) |

---

## 🚀 Getting Started

No installation needed. Just open in a browser.

```bash
# Clone the repository
git clone https://github.com/ayankhan964825-lab/project-2-.git
cd project-2-
```
Or use VS Code Live Server for local development:
`Right-click index.html → "Open with Live Server"`

---

## 📄 Documentation
- `prd.md` — Product Requirements Document
- `trd.md` — Technical Requirements Document
- `DESIGN_SCHEMA.md` — Design System & Theme config
- `SYSTEM_ARCHITECTURE.md` — Architecture & Data Flow

## 📃 License
MIT License — free to use, modify, and distribute.
