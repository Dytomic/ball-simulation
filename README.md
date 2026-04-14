# Ball Physics Simulation (Game Dev Interview Starter)

**Live technical interview starter for a game-developer role at [Dytomic](https://dytomic.com). Authored by [Mourad Elsheraey](https://github.com/elsheraey), a co-founder at Dytomic, as a reusable hiring artefact.**

> This repo is a deliberately incomplete starter. Candidates extend it during a live interview session against the clock.

## What candidates receive

A browser-based physics sandbox that, out of the box, does:

- **1,000 footballs** rendered across a full-viewport green field
- Each ball starts with a random initial force
- **Gravity** applied uniformly each frame (9.81 m/s²)
- **Mass** (uniform 2 kg) affects the force-to-acceleration ratio per Newton's second law
- **Boundary collision** with walls, floor, and ceiling (velocity component flips on contact)
- **GPU-accelerated rendering** via CSS `translateX/Y/Z(0)` transforms
- A simulation loop targeting 60 FPS (`setInterval` at 16 ms)

## What candidates are asked to do

The starter has one deliberate gap: `checkCollisions()` is stubbed.

Implementing ball-to-ball collision detection is the live-interview task. At 1,000 balls, a naive O(n²) approach blows up; the interview explores the candidate's instincts around:

- Spatial partitioning (quadtree, uniform grid, spatial hashing)
- Collision detection vs. resolution (ordering, impulses, restitution, coefficient of restitution)
- Performance intuition under a 16 ms frame budget
- Code organisation and clarity while the clock runs

There's no single correct answer. The interview is about reasoning and trade-offs, not a reference implementation.

## Files

| File | Purpose |
|------|---------|
| `main.html` | Entry point. Full-viewport green field container. |
| `simulation.js` | `Ball` class, physics loop, collision stub. |
| `football.png` | Ball sprite. |

## Running it

No build step, no server required. Open `main.html` directly in any modern browser, or serve locally:

```bash
python3 -m http.server 8080
# open http://localhost:8080/main.html
```

## Known limitations (by design)

- `checkCollisions()` is the candidate task, not a bug.
- No spatial partitioning is provided; the candidate decides what's worth it.
- Container size is captured once at load and doesn't respond to window resize.

## License

Owned by Dytomic. Interview candidates are welcome to fork for the purposes of completing the exercise.
