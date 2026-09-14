<div align="center">

# 🐦 Flappy Bird Arcade

**A polished, zero-dependency, retro arcade recreation of the classic endless flyer.**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](#)
[![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](#license)

[Play Demo](#quick-start) • [Features](#key-features) • [Controls](#controls) • [Architecture](#architecture--tech-stack) • [Customization](#customization)

---

</div>

## 🎮 About the Game

**Flappy Bird Arcade** brings the iconic 2013 mobile sensation into modern browsers with responsive canvas physics, smooth procedural animations, and zero external asset dependencies. Built as a single self-contained application, it integrates synthesized chiptune audio via the Web Audio API, dynamic particle effects, and tiered medal achievements.

---

## ✨ Key Features

- **🎨 Pure Canvas & Vector Rendering:** The bird, pipes, clouds, skyline, and ground are drawn procedurally via Canvas 2D—no external PNGs or spritesheets required.
- **🔊 Web Audio API Sound FX:** Synthesized retro jump whooshes, point chimes, crash sounds, and UI clicks without latency or audio asset loading issues.
- **✨ Micro-Interactions & Game Feel:**
  - Screen shake & flash hit effects on collision.
  - Feather particles dropped upon each flap.
  - Score burst particle explosion on clearing pipes.
  - Smooth rotation physics based on vertical velocity.
- **🏆 Progression & Medal System:**
  - 🥉 **Bronze:** 5+ points
  - 🥈 **Silver:** 10+ points
  - 🥇 **Gold:** 25+ points
  - 👑 **Platinum:** 40+ points
  - Persistent High Score saved via browser `localStorage`.
- **⚙️ Difficulty Modes:**
  - **Casual:** Wider gaps, gentler gravity, slower pipe speed.
  - **Normal:** The classic arcade balance.
  - **Hard:** Narrow clearances and aggressive pacing for seasoned players.
- **📱 Universal Compatibility:** Fully responsive touch controls for mobile screens alongside standard mouse/keyboard input for desktop.

---

## 🕹️ Controls

| Platform | Action | Input |
|---|---|---|
| **Desktop** | Flap / Jump | <kbd>Space</kbd>, <kbd>↑ Up Arrow</kbd>, or Left Click |
| **Mobile / Tablet** | Flap / Jump | Tap anywhere on screen |
| **UI** | Restart Game | Click <kbd>Play Again</kbd> or press <kbd>Space</kbd> |
| **Settings** | Audio & Difficulty | Click top-left header buttons |

---

## 🚀 Quick Start

No build step, Node environment, or bundler is required. 

### Option 1: Direct Play
Simply clone the repository and open `index.html` in any modern web browser:

```bash
# Clone the repository
git clone https://github.com/your-username/flappy-bird-arcade.git

# Navigate into directory
cd flappy-bird-arcade

# Open index.html in your default browser (macOS)
open index.html

# On Linux
xdg-open index.html

# On Windows
start index.html
```

### Option 2: Run with a Local Server
If testing audio policies or hosting locally:

```bash
# Using Python 3
python -m http.server 8080

# Or using Node npx
npx serve .
```
Visit `http://localhost:8080` in your browser.

---

## 🛠 Architecture & Tech Stack

```
flappy-bird-arcade/
├── index.html        # Single-file architecture (Canvas engine, UI overlays, CSS, Audio)
└── README.md         # Documentation & setup guide
```

- **Core Engine:** HTML5 Canvas API running on `requestAnimationFrame` with fair circle-to-AABB collision hitboxes.
- **Styling & UI:** Tailwind CSS (via CDN), Google Fonts (`Press Start 2P`, `Fredoka`), and FontAwesome icons.
- **Audio Engine:** Custom `RetroAudioEngine` class harnessing `AudioContext` oscillators (`sine`, `triangle`, `sawtooth`) and gain nodes.
- **Resolution Strategy:** Internal fixed coordinate plane (`380 x 640`) mapped with `window.devicePixelRatio` scaling to eliminate blur on retina displays.

---

## ⚙️ Customization

You can tweak gameplay balance directly in `index.html`:

```javascript
const DIFFICULTIES = [
  { name: 'Casual', gap: 170, speed: 2.2, gravity: 0.32, flap: -6.5 },
  { name: 'Normal', gap: 145, speed: 2.7, gravity: 0.38, flap: -7.5 },
  { name: 'Hard',   gap: 125, speed: 3.2, gravity: 0.44, flap: -8.0 }
];
```

- **`gap`**: Distance (in px) between top and bottom pipes.
- **`speed`**: Horizontal scroll velocity of pipes and ground.
- **`gravity`**: Downward acceleration per tick.
- **`flap`**: Instant upward impulse applied when jumping.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

Made with 💛 and HTML5 Canvas. Star ⭐ the project if you enjoyed playing!

</div>