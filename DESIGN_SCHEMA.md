# FestiveLink — Design Schema

## 1. Visual Aesthetics
- **Core Theme**: High-contrast dark mode foundation with glassmorphism for forms, and full vibrant themes for viewer pages.
- **Typography**: 
  - Main Body: `Poppins` (clean, modern interface).
  - Highlights/Greetings: `Baloo 2` (curvy, energetic, festive feel).

## 2. Occasion Configuration Matrix

| Occasion | Key | Primary Color | Theme Gradient | Animation |
|:---:|:---:|:---:|:---:|:---:|
| Holi | `holi` | `#FF6B6B` | Colorful Red/Yellow | Confetti |
| Diwali | `diwali` | `#FFD700` | Golden/Deep Purple | Fireworks |
| Eid | `eid` | `#C0A060` | Deep Green/Gold | Stars |
| Ramzan | `ramzan` | `#1E5F74` | Deep Blue/Gold | Stars |
| Christmas | `christmas` | `#C0392B` | Green/Red | Snow |
| New Year | `newyear` | `#F39C12` | Dark Navy/Gold | Fireworks |
| Navratri | `navratri` | `#9B59B6` | Vibrant Purple | Confetti |
| Onam | `onam` | `#27AE60` | Kerala Green/Yellow | Petals |
| Lohri | `lohri` | `#E67E22` | Deep Red/Orange | Fire Elements |
| Birthday | `birthday` | `#E91E63` | Pink Gradient | Confetti (Pink/Gold) |
| Wedding | `wedding` | `#D4AF37` | Royal Dark Brown | Twinkling Stars |
| Anniversary | `anniversary` | `#E74C3C` | Romantic Red | Confetti (Red/Rose) |
| Graduation | `graduation` | `#3498DB` | Academic Blue | Confetti (Blue/Gold) |
| Baby Shower | `babyshower` | `#FF9FF3` | Pastel Pink/Blue | Floating Petals |
| Thank You | `thankyou` | `#1ABC9C` | Elegant Teal | Twinkling Stars |

## 3. UI Components
- **Creator UI `index.html`**:
  - Gradient title
  - CSS Grid interface for the occasion selector cards
  - Neumorphic glass form inputs
  - Real-time WhatsApp share button
- **Viewer UI `view.html`**:
  - Full-screen CSS linear/radial gradient determined by occasion class.
  - Interactive Canvas particle background
  - Overlay animated popup card (bounce-in) with greeting message.
