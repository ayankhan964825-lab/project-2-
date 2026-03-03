# FestiveLink — Technical Requirements Document (TRD)

## 1. Architecture
Serverless Static SPA. Only HTML, CSS, and JS files.

## 2. Tech Stack
- **HTML5**: Semantic structure.
- **CSS3**: Variables, Flexbox/Grid, Animations.
- **JavaScript (ES6+)**: DOM manipulation, Canvas rendering, Base64 encoding/decoding.

## 3. Data Model Strategy (URL Encoding)
State is passed from creator to viewer purely via URL parameters.
- **Format**: JSON object `{"sender": "...", "receiver": "...", "message": "...", "festival": "...", "version": "1.0"}`
- **Encoding Pipeline**: `JSON.stringify` -> `encodeURIComponent` -> `btoa`
- **Decoding Pipeline**: `atob` -> `decodeURIComponent` -> `JSON.parse`

## 4. Application Logic
### `index.html` (Creator)
- **Validation**: Ensures all fields are filled before generating the link.
- **Character Limit**: Real-time counter for the 500-char message limit.
- **Link Generation**: Constructs the `/view.html?d=` URL.
- **Clipboard API**: Copies the generated link.
- **WhatsApp Intent**: Creates a `wa.me` URL with pre-filled text.

### `view.html` (Viewer)
- **Initialization**: Parses the `?d=` parameter on load.
- **Error Handling**: Displays an error UI if the URL is invalid, tampered, or missing data.
- **Theming Engine**: Applies specific CSS classes to `<body>` and `.popup` based on the occasion key.
- **Particle Engine**: Initializes a Canvas 2D context to render specific particle types (confetti, fireworks, stars, petals, snow, fire).
