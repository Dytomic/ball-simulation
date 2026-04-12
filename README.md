# Ball Physics Simulation

A browser-based physics simulation built as part of a live technical interview for a game developer position at Dytomic.

## Demo

Open `main.html` in any modern browser — no build step or server required.

## What it does

Spawns 1,000 footballs across a full-viewport green field, each with a random initial force applied. Every ball is governed by:

- **Gravity** — 9.81 m/s² applied each frame
- **Mass** — uniform 2 kg, affects force-to-acceleration ratio (Newton's 2nd law)
- **Boundary collision** — velocity component flipped on wall/floor/ceiling contact
- **GPU-accelerated rendering** — position updates via CSS `translateX/Y/Z(0)` transforms

The simulation runs at a target of 60 FPS using `setInterval` at 16 ms intervals.

## Structure

| File | Purpose |
|------|---------|
| `main.html` | Entry point — full-viewport green field container |
| `simulation.js` | `Ball` class + physics loop + collision stub |
| `football.png` | Ball sprite |

## Known limitations / TODOs

- `checkCollisions()` is stubbed — ball-to-ball collision detection not implemented
- No spatial partitioning (e.g. quadtree) — O(n²) collision check would be needed for 1,000 balls
- Container size is captured once at load; does not respond to window resize
