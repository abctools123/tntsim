# 💥 TNTSim — Blast Physics Simulator

A real-time TNT explosion simulator that runs directly in your browser. Build structures, place TNT, and watch chain reactions destroy everything using raycast-based explosion physics.

**[▶ Play Now](https://abctools123.github.io/tntsim/)**

![TNTSim Screenshot](https://img.shields.io/badge/status-live-brightgreen) ![license](https://img.shields.io/badge/license-MIT-blue)

---

## Features

- **Real-time explosion physics** — 360° raycasting with variable strength decay per block type
- **Chain reactions** — exploding TNT triggers nearby TNT blocks
- **4 block types** — Stone, TNT, Obsidian, Bedrock (each with different blast resistance)
- **Particle effects** — colored explosion particles with gravity and fade
- **Screen shake** — camera shake on detonation
- **Camera controls** — WASD pan, mouse wheel zoom, smooth camera tracking
- **Brush tool** — place/remove multiple blocks at once (`[`/`]` to resize)
- **Performance HUD** — live FPS, MSPT (ms per tick), active TNT count
- **Mobile support** — touch controls for phones and tablets

---

## Controls

| Input | Action |
|-------|--------|
| **Left Click** | Place selected block |
| **Right Click** | Remove block |
| **Middle Click** | Prime TNT (ignite) |
| **Space** | Start / Pause simulation |
| **R** | Reset simulation |
| **1-4** | Select block type |
| **[ / ]** | Change brush size |
| **+ / -** | Change tick speed |
| **WASD / Arrows** | Pan camera |
| **Mouse Wheel** | Zoom in/out |
| **G** | Toggle grid |
| **H** | Toggle help |
| **.** (period) | Single-step tick (when paused) |

---

## Block Types

| # | Block | Color | Blast Resistance |
|---|-------|-------|-----------------|
| **1** | Stone | Gray | 1.5 strength |
| **2** | TNT | Red/White | Ignites on contact |
| **3** | Obsidian | Dark Purple | 3.0 strength |
| **4** | Bedrock | Black | 4.0+ strength |

---

## How It Works

Each explosion casts rays in a circle (360°). Each ray travels outward, losing strength as it destroys blocks:

- **Stone** absorbs 1.5 strength per block
- **TNT** ignites immediately (spawning a primed TNT entity with reduced fuse)
- **Obsidian** absorbs 3.0 strength — only powerful blasts break it
- **Bedrock** requires 4.0+ strength — nearly indestructible

Primed TNT entities count down their fuse each tick before detonating. When chain reactions are enabled, destroyed TNT blocks spawn new primed TNT entities at their location, creating cascading destruction.

---

## Tech Stack

- **Pure HTML5 Canvas** — no frameworks, no dependencies, no build step
- **Vanilla JavaScript** — self-contained single file
- **GitHub Pages** — instant deployment from `main` branch
- **Share Tech Mono + Inter** — Google Fonts for the monospace HUD

---

## Run Locally

```bash
# Clone the repo
git clone https://github.com/abctools123/tntsim.git
cd tntsim

# Serve with any static server
python3 -m http.server 8000
# or: npx serve .
# or: open index.html directly

# Open http://localhost:8000
```

---

## Desktop Versions

The original Windows executable (`.NET 7.0 NativeAOT`) and a cross-platform Python+raylib reimplementation are also available:

| Platform | Method |
|----------|--------|
| **Web** | [Play in browser](https://abctools123.github.io/tntsim/) |
| **Windows** | Run `TNTSim.exe` (requires raylib.dll in same folder) |
| **Linux/macOS/Windows** | `pip install raylib && python tntsim_crossplatform.py` |
| **Linux/macOS (via Wine)** | `./run_tntsim_wine.sh` |

See the [release page](https://github.com/abctools123/tntsim/releases) for downloads.

---

## License

MIT — build, modify, share freely.

---

*Original TNTSim by Techcraft7. Web port & cross-platform version by OpenHands.*