⚡ Reaction Timer 3D
A retro-futuristic reflex test built with Vanilla JavaScript and Three.js.
A browser-based 3D game designed to test human reaction speeds. The application renders an interactive glowing icosahedron that changes state based on game logic, utilizing raycasting for interaction and the Web Audio API for sound synthesis.

🎮 Features
Interactive 3D Scene: Features a multi-layered Icosahedron (Core, Wireframe, Glass Shell) with dynamic lighting.
State Management: Handles complex game states (Idle, Waiting, Ready, Result, Error) with visual feedback.
Raycasting: Accurate click/touch detection on 3D objects using Three.js Raycaster.
Web Audio API: Synthesized procedural sound effects for success and error states (no external audio files required).
Persistence: Saves session statistics (Best, Worst, Average times) to the browser's LocalStorage.
Responsive Design: Fully adaptive 3D camera positioning and UI for desktop, tablets, and mobile devices.
Neon Aesthetic: Custom CSS variables for a consistent "Cyberpunk" arcade theme.
🕹️ How to Play
Start: Click (or tap) the floating blue shape.
Wait: The shape will turn RED. Do not click yet!
React: Wait for the random timer... as soon as the shape turns GREEN, click it!
Result: Your reaction time is displayed in milliseconds.
Penalty: Clicking while the shape is red causes a "False Start."
🚀 Installation & Setup
Important Note: Because this project uses ES6 Modules (type="module") to import Three.js, you cannot simply open the index.html file directly in your browser (using the file:// protocol). You must run it via a local web server to avoid CORS errors.
Option A: VS Code (Recommended)
Install the Live Server extension by Ritwick Dey.
Right-click index.html and select "Open with Live Server".
Option B: Python
If you have Python installed, navigate to the folder in your terminal and run:
Bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

Then open http://localhost:8000 in your browser.
Option C: Node.js
If you have Node.js installed:
Bash
npx http-server .

⚙️ Configuration
The game logic is designed to be easily tunable. Look for the CONFIG constant at the top of the JavaScript section to adjust gameplay parameters:
JavaScript
const CONFIG = {
    // Adjust difficulty
    MIN_WAIT_TIME: 2000, 
    MAX_WAIT_TIME: 5000,
    
    // Change aesthetic
    COLORS: {
        IDLE: 0x00d4ff,    // Blue
        WAITING: 0xff3366, // Red
        READY: 0x00ff88,   // Green
    },
    
    // Adjust camera for different fields of view
    CAMERA: {
        FOV: 60,
        POSITION_Z: 5
    }
    // ... animation speeds, etc.
};

📂 Code Structure
Since the project is contained within a single HTML file for portability, the code is organized into distinct logical sections:
CSS: Custom properties (Variables) for theming, responsive media queries, and UI overlays.
HTML: Canvas container, HUD overlays, and Modals.
JS (Module):
Imports: Three.js via CDN.
GameState: Tracks timing, phases, and flags.
AudioSystem: Procedural sound generation.
SessionStats: LocalStorage wrapper.
Three.js Setup: Scene, Camera, Renderer, Lighting.
Mesh Construction: creation of the 3-layer sphere.
Animation Loop: requestAnimationFrame handling.
🛠️ Browser Support
Chrome/Edge: Full support (Desktop & Mobile).
Firefox: Full support.
Safari: Full support (macOS & iOS).
Requires WebGL support (standard in all modern browsers).
📄 License
This project is open-source and free to use for educational or portfolio purposes.
