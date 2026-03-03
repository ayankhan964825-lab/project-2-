# FestiveLink — Product Requirements Document (PRD)

## 1. Product Overview
FestiveLink is a serverless, browser-based web application that lets anyone create a personalized greeting page for festivals and life events and share it as a unique link. 

## 2. Target Audience
- Individuals celebrating cultural festivals (Holi, Diwali, Eid, Christmas, etc.)
- People sending wishes for life events (Birthdays, Weddings, Anniversaries, Graduations, etc.)

## 3. Core Features
- **Occasion Selection**: 15 distinct occasions (9 festivals + 6 life events).
- **Personalization**: Sender and receiver names, plus a custom message (up to 500 chars).
- **URL Encoding**: All data is encoded directly into the URL (Base64), requiring zero backend.
- **Themed Landing Pages**: Each occasion has a unique background, popup style, and text colors.
- **Particle Animations**: Canvas-based animations specific to the occasion (confetti, fireworks, stars, petals, snow, fire).
- **WhatsApp Integration**: One-click sharing to WhatsApp with a pre-filled message.

## 4. User Flows
### Creator Flow
1. Open FestiveLink.
2. Select an occasion from the grid.
3. Enter Sender Name, Receiver Name, and Message.
4. Click "Generate Greeting Link".
5. Copy the generated link or share via WhatsApp.

### Viewer Flow
1. Click the shared link.
2. See a full-screen themed background with particle animations.
3. View the personalized greeting popup.
4. Click "Create Your Own FestiveLink" to become a creator.

## 5. Non-Functional Requirements
- **Serverless Architecture**: 100% static HTML, CSS, JS. No server, database, or API required.
- **Performance**: High frame rate (>30 FPS) for canvas animations on mobile.
- **Responsive Design**: Mobile-first UI scaling up to desktop.
- **Security**: No data storage, no tracking, strict URL parameter validation to prevent XSS.
