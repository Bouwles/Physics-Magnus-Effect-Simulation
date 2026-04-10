# Magnus Effect — Spinning Ball Physics Simulation

An interactive 3D physics simulation of the Magnus Effect.

---

## About

This simulation visualises the forces acting on a spinning ball in flight. Gravity, aerodynamic drag, and the Magnus force in real time using accurate SI physics equations. 

**Made by:** Paul Nercessian
**For:** Richard Abou Jamra's Physics Extended Essay

---

## What is the Magnus Effect?

The Magnus Effect is the phenomenon where a spinning object moving through a fluid (such as air) experiences a lateral force perpendicular to both its velocity and its axis of rotation. This is why a spinning football curves mid-flight, a sliced tennis ball dips, or a baseball pitcher can throw a curveball.

The force arises because spin creates an asymmetry in the airflow around the ball. One side experiences higher pressure, the other lower generating a net lift force.

---

## Physics Engine

All forces are computed every frame using real equations. Nothing is fixed, making it decently realistic to how the ball would move in real life.

| Force | Equation |
|---|---|
| Gravity | `F = m × g` |
| Drag | `F = 0.5 × ρ × Cd × A × v²` |
| Magnus | `F = 0.5 × ρ × CL × A × r × (ω × v)` |
| Spin decay | `ω = ω × (1 − μ × dt)` |

- **ρ** — fluid (air) density
- **Cd** — drag coefficient (~0.47 for a sphere)
- **CL** — lift coefficient
- **A** — cross-sectional area (π r²)
- **ω** — angular velocity vector (rad/s)
- **v** — linear velocity vector
- **μ** — viscous damping factor

Integration uses Euler stepping with a capped timestep of 20 ms per frame for numerical stability.

---

## Features

- Real-time 3D rendering via Three.js
- Live force vector arrows (velocity, gravity, drag, Magnus)
- Ball trail + ground shadow trail
- Live telemetry HUD (speed, angular velocity, position, elapsed time)
- Fully configurable parameters via side panel:
  - Fluid density, mass, radius, gravity, viscosity
  - Initial position, velocity, angular velocity and spin axis
- Camera controls: orbit (mouse), pan (right-click drag), zoom (scroll), WASD translate, arrow key orbit
- Follow Ball and Top View camera presets
- Adjustable camera rotation sensitivity

---

## How to Run

Open `index.html` directly in any modern browser.

```
index.html   <-- download and open the file
```

---

## Controls

| Input | Action |
|---|---|
| Left-click drag | Orbit camera |
| Right-click drag | Pan camera |
| Scroll wheel | Zoom |
| W / S | Move camera forward / backward |
| A / D | Strafe camera left / right |
| Arrow keys | Orbit camera |
| Launch | Start simulation with current settings |
| Pause | Pause / resume |
| Reset | Reset ball and trails |
| Follow Ball | Snap camera behind ball |
| Top View | Bird's-eye view above ball |
| Panel | Toggle settings panel |

---

## Tech Stack

- [Three.js r134](https://threejs.org/) for 3D rendering
- Vanilla HTML + CSS + JavaScript
- Google Fonts
- OrbitControls
