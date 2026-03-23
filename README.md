# 3D Missile Defense — Guidance Algorithm Lab

> An interactive 3D simulation where you defend a city against incoming missile threats using real guidance algorithms.
> Inspired by real-world air defence engagements, 2024–2025.

**[Live Demo →](https://manoj-kumar-portfolio-hub.vercel.app/)**

---

## What is this?

This is a browser-based simulation that puts you in the seat of an air defence operator. Ballistic and cruise missiles are inbound. You choose the guidance law, tune the interceptor, and launch. The maths is real — the same equations that run in actual missile defence systems.

The scenario is drawn from real events: saturation attacks involving hundreds of simultaneous tracks, where the difference between a city standing and a city burning came down to a guidance algorithm running in milliseconds.

---

## Features

- **5 Guidance Laws** — Pure Pursuit, Proportional Navigation, Augmented PN, Lead Pursuit, Command Line-of-Sight (CLOS)
- **4 Threat Types** — SRBM, MRBM, ICBM, Cruise Missile (different speeds, altitudes, and flight arcs)
- **3D Visualisation** — Three.js rendered scene with orbit, pan, and zoom controls
- **Live Radar** — Mini radar overlay with real-time track positions
- **HUD** — Time, threat count, interceptor count, nearest miss distance, kills vs hits, time-to-impact
- **Threat Alarm System** — Pulsing border + banner on new inbound track
- **Adjustable Parameters** — Speed, gravity, turn rate, kill radius, PN constant (N), time scale
- **Auto-intercept mode** — Fires immediately on threat spawn
- **Click-to-place** — Set threat launch origin by clicking the ground
- **City consequence model** — Misses hit the city; asymmetric cost shown ($3.5M interceptor vs $50K threat)

---

## Guidance Algorithms

| ID | Name | Description |
|----|------|-------------|
| PP | Pure Pursuit | Steers directly toward target position each frame |
| PN | Proportional Navigation | Steers proportional to line-of-sight rotation rate — the standard for most real interceptors |
| APN | Augmented PN | Adds target acceleration correction to PN — used in modern systems |
| LP | Lead Pursuit | Aims at a predicted future position (lead angle) |
| CLOS | Command Line-of-Sight | Keeps interceptor on the line between launcher and target |

---

## Controls

| Input | Action |
|-------|--------|
| Left drag | Orbit camera |
| Right drag | Pan camera |
| Scroll | Zoom |
| `A` | Spawn threat |
| `I` | Launch interceptor |
| `Space` | Pause / Resume |
| `1` – `4` | Switch threat type |
| `[` / `]` | Decrease / Increase time scale |
| Click ground | Set threat launch point |

---

## Tech Stack

- **Three.js r128** — 3D rendering (loaded from CDN)
- **Vanilla JS** — No framework, no build step
- **Single HTML file** — Everything in `index.html`
- **Google Analytics** — Page-level analytics via gtag.js

---

## Running Locally

No build step needed. Just open in a browser:

```bash
# Option 1: open directly
open index.html

# Option 2: serve locally (avoids any CORS issues with SVG map loading)
npx serve .
# or
python3 -m http.server 8080
```

---

## About the Author

**Manoj** — researcher, builder, curious about the intersection of conflict, technology, and decision-making under pressure.

- GitHub: [github.com/manojrammurthy](https://github.com/manojrammurthy)
- Twitter/X: [@manojrammoorthy](https://x.com/manojrammoorthy)
- Website: [manoj-kumar-portfolio-hub.vercel.app](https://manoj-kumar-portfolio-hub.vercel.app/)

---

## License

MIT — do whatever you want with it, just don't use it to actually launch missiles.
