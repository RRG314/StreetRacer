
# Street Racer (Beta) — Real-World Map Racing

Street Racer is a browser-based racing game where *real cities become the tracks*.

Instead of handcrafted levels, Street Racer loads live street geometry from OpenStreetMap and turns actual places into playable race environments. Every curve, intersection, and grid comes from the real world. You are not driving on a theme. You are driving a place.

This build represents a fully playable beta with multiple cities, game modes, police chases, custom tracks, and real map imagery.

Play here:  
https://rrg314.github.io/StreetRacer/

---

## Current Cities

- Baltimore, MD  
- Hollywood, CA  
- New York, NY  
- Miami, FL  
- Tokyo, Japan  
- Monaco  
- Nürburgring  

You can also:
- Search for any city by name  
- Enter custom latitude/longitude  
- Adjust the load radius from 1–10 miles  

Any mapped location can become a race environment.

---

## Game Modes

- **Free Roam**  
  Explore the city freely. Learn the streets, test speed, and drive without pressure.

- **Time Trial**  
  Race across the city to a dynamically chosen destination as fast as possible.

- **Checkpoints**  
  Collect markers scattered across real neighborhoods. Finish when all are cleared.

Each mode includes its own HUD behavior, timer, and results screen.

---

## Controls

### Driving
- **W / ↑** – Accelerate  
- **S / ↓** – Brake / Reverse  
- **A / ←** – Turn Left  
- **D / →** – Turn Right  
- **Space** – Handbrake  
- **Ctrl** – Boost  
- **Shift** – Off-Road Mode  

### Camera & View
- **Mouse Drag** – Pan camera  
- **Mouse Wheel / +/-** – Zoom  
- **R** – Reset zoom  
- **Esc** – Pause menu  

---

## Features

- Real street layouts generated from OpenStreetMap  
- Live street and satellite map imagery  
- Multiple cities with unique layout and feel  
- Full menu system and game flow  
- Police chase system with pursuit and capture  
- Boost, drifting, and off-road driving  
- Dynamic camera and minimap  
- HUD with speed, speed limit, heading, coordinates, and street name  
- Smarter spawning on valid streets  
- Results screens for timed modes  
- Custom track recording  
  - Draw your own track by driving  
  - Start/finish markers  
  - Loop detection  
  - Tracks behave like real roads  


---

## Status

Street Racer is in **early beta**.

It is fully playable end-to-end, but still being refined. Real-world map data can be unpredictable. In rare cases, streets may not line up perfectly on first load. If that happens, click **Reload Map** and they will align correctly.

Performance may vary depending on location, radius, and machine.

---

## Vision

Street Racer is built around a simple idea:

**The real world is the racetrack.**

This 2D version establishes the foundation. The long-term direction includes:

- Full cities like Los Angeles, Chicago, and beyond  
- European, Middle Eastern, and Asian cities  
- Smaller towns and rural areas  
- Structured race routes based on real geography  
- Traffic, vehicle damage, and deeper physics  
- Car selection and customization  
- Shared worlds and multiplayer  
- A full 3D version where players can drive through their own streets  

The goal is not just another racing game, but a new way to experience the world through motion.

---

## Running Locally

You can open `index.html` directly, but some browsers restrict network access from `file://`.

Recommended:

```bash
python -m http.server
````

Then open:

```
http://localhost:8000
```

---

## Open Data & Attribution

Street geometry is sourced from **OpenStreetMap contributors**.
Road data is retrieved via the **Overpass API**.

© OpenStreetMap contributors
[https://www.openstreetmap.org](https://www.openstreetmap.org)

This project uses map data at runtime and does not redistribute a derived database.

