
# StreetRacer

**StreetRacer** is a browser-based 3D driving and racing prototype that streams real-world road data from OpenStreetMap and renders it as a drivable city environment using Three.js. The project focuses on fast iteration, spatial awareness, and arcade-style vehicle control rather than full physical simulation.

Author: Steven Reid

---

## Overview

StreetRacer is a single-file HTML application that:

- Loads real streets and buildings from OpenStreetMap (via Overpass)
- Converts geographic data into a local 3D driving space
- Renders roads as wide ribbon meshes instead of simple lines
- Simulates an arcade-style car with steering, drift, boost, and braking
- Includes multiple gameplay modes and a live minimap
- Runs entirely in the browser with no build step

This project is experimental and intended as a foundation for further work on road-constrained driving, navigation, and large-scale spatial interaction.

---

## Features

### World generation
- Streams nearby roads (`highway=*`) and buildings (`building=*`) from OpenStreetMap
- Supports multiple predefined cities and custom location search
- Automatically retries with larger areas if initial queries return sparse data
- Converts latitude/longitude to a local X/Z coordinate space

### Roads
- Roads are rendered as flat ribbon meshes with real width
- Each road stores:
  - type (motorway, primary, residential, etc.)
  - approximate width
  - approximate speed limit
  - street name (when available from OSM)
- A spatial grid is built to accelerate nearest-road queries

### Buildings
- Simplified 3D blocks derived from OSM building footprints
- Height based on tags or reasonable defaults
- Building count capped for performance

### Driving & gameplay
- Arcade vehicle model (not a physics engine)
- Speed-dependent steering and grip
- Drift behavior with handbrake
- Boost system
- Soft road-constraining logic (can be overridden with off-road mode)

### Game modes
- Free Roam
- Time Trial (reach a destination within a time limit)
- Checkpoints
- Optional police chase mode with pursuit behavior

### UI & tools
- HUD showing speed, speed limit, street name, drift angle, boost
- Live minimap with nearby roads and objectives
- Track recording mode that draws your driven path as a ribbon
- Multiple camera modes

---

## Controls

### Driving
- **W / Up Arrow** — Accelerate
- **S / Down Arrow** — Brake / reverse
- **A / Left Arrow** — Steer left
- **D / Right Arrow** — Steer right
- **Space** — Handbrake / drift
- **Ctrl** — Boost
- **Shift** — Off-road mode (reduces road clamping)

### Camera
- **C** — Cycle camera views
- **V** — Look backward

### Game
- **R** — Toggle track recording
- **N** — Load next city
- **Esc** — Pause menu

---

## Running the project

### Local server (recommended)

Because the app fetches external data, it must be served over HTTP.

**Python**
```bash
python -m http.server 8000
````

Open:

```
http://localhost:8000/street-racer-3d-v17.html
```

**Node**

```bash
npx serve .
```

### GitHub Pages

1. Push the repository to GitHub as `StreetRacer`
2. Enable GitHub Pages for the main branch
3. Open the generated Pages URL

---

## Data sources

StreetRacer relies on public services:

* OpenStreetMap (road and building data)
* Overpass API (OSM queries)
* Nominatim (city search / geocoding)

These services are subject to rate limits and availability. Loading failures or delays can occur if services are busy or throttled.

---

## Known limitations

* Roads are visual surfaces; the car still moves on a single ground plane
* Road enforcement is currently **soft**, not a hard physical constraint
* No full collision system (buildings are not solid barriers)
* Driving behavior is arcade-style, not realistic vehicle physics
* OSM coverage quality varies by location
* Large areas can impact performance

---

## Project structure

Single-file application:

* `street-racer-3d-v17.html`

All logic, rendering, UI, and styles are contained in this file.

---

## Intended future improvements

* Stronger road corridor enforcement
* Better lane-aware driving behavior
* Improved collision handling
* Smarter AI traffic and police logic
* More stable large-area streaming
* Visual polish and performance tuning

---

## License

**All Rights Reserved**

This source code and associated assets are the exclusive property of Steven Reid.

No permission is granted to copy, modify, redistribute, sublicense, or use this software or its derivatives for commercial or non-commercial purposes without explicit written permission from the author.

---

## Disclaimer

This project is experimental and provided as-is. It is not affiliated with OpenStreetMap, Overpass, Nominatim, or Three.js.

```
