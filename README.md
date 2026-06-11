# Dusttown

A tactical bomb-defusal FPS that runs entirely in your browser — one HTML file, zero dependencies to install, nothing to build.

**▶ Play it here:** https://jemappellesami.github.io/dusttown/

*(Desktop only — requires mouse + keyboard and pointer lock.)*

![Genre](https://img.shields.io/badge/genre-tactical%20FPS-orange)
![Engine](https://img.shields.io/badge/engine-Three.js-blue)
![Size](https://img.shields.io/badge/size-~64KB-green)

## The mission

You're alone in **Dusttown**, a sun-bleached desert town held by four hostiles. A charge is armed at the bombsite and the timer is running.

**Win** by defusing the charge or eliminating every hostile.
**Lose** if you go down — or the timer hits zero.

## Controls

| Key | Action |
|---|---|
| `W A S D` | Move |
| `Mouse` | Look / aim |
| `Left click` | Fire |
| `Shift` (hold) | Quiet walk — smaller noise radius |
| `Space` | Jump |
| `R` | Reload |
| `E` (hold 5s) | Defuse at the bombsite |
| `Esc` | Pause |

**Tactical tip:** the bots hear you. Sprinting broadcasts your position; quiet-walking lets you reposition unseen. Taking damage interrupts a defuse, so clear the area first — or gamble.

## Features

- **Bot AI with a real state machine** — patrol, alert, engage, hunt. Bots use raycast line-of-sight (no seeing through walls), human-like reaction delays, burst fire that tightens over time, and they seek cover and reposition mid-fight.
- **A\* pathfinding** on the same grid that drives collision — bots navigate corridors and flank rather than walking into walls.
- **Recoil that matters** — a 30-round climbing/weaving spray pattern, bloom-based spread, tracers, distance damage falloff, and 4× headshots.
- **Fully procedural everything** — every texture is generated on a canvas, every sound is synthesized with the Web Audio API (stereo-panned by source position), every model is built from math. There are no asset files because there are no assets.
- **Game feel** — screen shake, viewmodel sway, directional damage indicators, low-health vignette, expanding crosshair, accelerating bomb beeps, and a monospace tactical HUD with a killfeed.

## Running it

Just open the page linked above — or clone the repo and double-click `index.html`. That's it. The only external resource is Three.js, loaded from a CDN.

```bash
git clone https://github.com/YOUR-USERNAME/dusttown.git
cd dusttown
# open index.html in any modern browser
```

## Tech notes

- **Three.js** (CDN) for rendering — ACES filmic tone mapping, soft shadows, instanced geometry for the level
- **Fixed-timestep simulation** (60Hz) decoupled from the render loop, so game logic is frame-rate independent
- The map is a 24×24 character grid that drives level geometry, collision, bot navigation, and line-of-sight checks from a single source of truth
- Single file, ~64KB of hand-rolled JavaScript

## License

MIT — do whatever you like with it.
