# FestiveLink — System Architecture

## Architecture Pattern
Serverless Static SPA (Single Page Application).

## Components
- **Hosting Strategy**: CDN caching via GitHub Pages, Netlify, or similar static hosting.
- **Client-Side Environment**: Modern web browsers (ES6+ support).

## Flow Diagram
1. **User Action**: Fills out `index.html` form.
2. **Encoding Module**: Generates Base64 encoded JSON string.
3. **URL Generation**: Appends encoded string as a `?d=` parameter.
4. **Copy & Share**: User copies or clicks "Share on WhatsApp".
5. **Receiver Action**: Opens the shared `/view.html?d=` link.
6. **Decoding Module**: Extracts the JSON data from `?d=`.
7. **Rendering Engine**: Renders dynamic themes, DOM manipulation, and Canvas animations based on specific occasion config.

## Performance Optimization
- Minimal HTTP requests: No external libraries required (pure CSS + Vanilla JS).
- Lightweight rendering: Direct DOM manipulation with localized reflows.
- Custom Canvas logic: Fast 60 FPS drawing loop with automated garbage collection for particle off-screen bounds.
