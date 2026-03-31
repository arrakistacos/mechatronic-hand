# 🤖 MECHATRONIC HAND v1.0

Real-time hand tracking + 3D mechatronic robot hand rendered in the browser.

## Live Demo

**[▶ Launch App](https://arrakistacos.github.io/mechatronic-hand/)**

## Tech Stack

- **MediaPipe Hands** — real-time 21-landmark hand tracking via webcam
- **Three.js** — procedural 3D mechatronic hand with metallic materials
- **UnrealBloom** — cyberpunk glow post-processing
- **No build tools** — single HTML file, all CDN imports

## Features

- Procedurally built robot hand with 5 fingers × 3 phalanges each
- Chrome/metal panels with emissive cyan edge glow
- Joint bends mapped from MediaPipe landmarks using dot-product angle math
- Lerp-smoothed animation (35% per frame)
- Wrist orientation tracking
- Cyberpunk HUD with live finger bend percentages
- Camera preview with landmark overlay
- Scanline overlay + bloom post-processing
- Demo mode when camera is unavailable

## How It Works

MediaPipe detects 21 hand landmarks from webcam. For each finger joint, the bend angle is computed using vector math between the three landmark points. These angles are mapped to `[0..1]` bend values and lerp-smoothed before being applied to Three.js bone rotations.
