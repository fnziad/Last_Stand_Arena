<p align="center">
  <h1 align="center">🎯 Target Frenzy 3D — Battle Royale Edition</h1>
  <p align="center">
    A fast-paced 3D arena shooter with battle royale mechanics, multi-weapon combat, and progressive difficulty — built entirely in Python with OpenGL.
  </p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.7+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/OpenGL-GLUT-5586A4?style=for-the-badge&logo=opengl&logoColor=white" alt="OpenGL"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License"/>
  <img src="https://img.shields.io/badge/Lines_of_Code-2600+-orange?style=for-the-badge" alt="LOC"/>
</p>

---

## About

**Target Frenzy 3D** is a complete 3D battle royale shooter game written from scratch in Python using OpenGL (via PyOpenGL and GLUT). It features a massive arena, 3 switchable weapons, 4 enemy AI types, a shrinking battle royale zone, power-ups with distinct 3D models, headshot mechanics, hit markers, floating damage numbers, and a full HUD with minimap.

> **Made by Fahad Nadim Ziad — 2026**

---

## Features

### 🔫 Multi-Weapon System

| Weapon            | Key | Damage | Fire Rate | Spread | Ammo | Special               |
| ----------------- | --- | ------ | --------- | ------ | ---- | --------------------- |
| **Pistol**        | `1` | 12     | Slow      | Tight  | 50   | Precise, quick reload |
| **Assault Rifle** | `2` | 10     | Fast      | Medium | 120  | Full-auto tracer      |
| **Shotgun**       | `3` | 8×6    | Very Slow | Wide   | 24   | 6 pellets per blast   |

- Press `R` to reload manually
- Auto-reload when magazine is empty
- Kills replenish ammo for all weapons
- Each weapon has a **unique first-person model** and **distinct projectile visuals**

### 🎯 Combat Mechanics

- **Headshot System** — Shots hitting the enemy head zone deal **2× damage** with red hit markers
- **Hit Markers** — White crosshair X-flash on body hits, red on headshots
- **Floating Damage Numbers** — Damage values pop up on screen with each hit
- **Kill Score Text** — Green "+points" floats up on eliminations
- **Muzzle Flash** — Visual flash overlay when firing

### 🏟️ Battle Royale Arena

- **Massive 10,000 × 10,000 unit arena** with green grass terrain
- **Shrinking Zone** — Forces players inward; outside zone = taking damage
- **80+ obstacle clusters** (crates) and **30 pillars** for tactical cover
- **Zone Warning System** — Flashing HUD alert when zone shrinks

### 👾 Enemy AI (4 Types)

| Type       | HP  | Speed | Behavior                        | Threat    |
| ---------- | --- | ----- | ------------------------------- | --------- |
| **Grunt**  | 30  | 3.5   | Direct chaser, moderate shooter | Medium    |
| **Tank**   | 80  | 1.8   | Slow, heavy armor, high damage  | High      |
| **Scout**  | 15  | 6.0   | Fast zigzag, agile dodger       | Medium    |
| **Sniper** | 25  | 1.2   | Keeps distance, high accuracy   | Very High |

- Enemies **scale in HP** per level (+12% per level)
- All enemies **shoot back** with type-specific accuracy and fire rates
- Progressive spawning with more snipers and tanks at higher levels

### ⬆️ Power-Ups (3D Visualized)

| Power-Up     | Shape                | Color  | Effect                   |
| ------------ | -------------------- | ------ | ------------------------ |
| Health Pack  | 3D Cross / Plus      | Green  | Restores 30 HP           |
| Speed Boost  | Spinning Diamond     | Blue   | 1.5× speed for 10s       |
| Damage Boost | Spiky Star           | Red    | 2× weapon damage for 10s |
| Shield       | Dome with Torus Ring | Yellow | 50 HP shield for 15s     |

Each power-up has a **pulsing glow ring** and **bobbing animation**.

### 📊 Scoring & Progression

- **Combo System** — Chain kills within 3s for up to **5× multiplier**
- **Kill Streaks** — Rampage (5), Unstoppable (10), Godlike (15) with bonus points
- **Headshot Bonus** — 1.5× score on headshot kills
- **Level System** — Kill enough enemies to advance; each level heals +20 HP
- **Post-Game Stats** — Score, kills, streak, combo, time survived, accuracy

### 🎨 Visual Features

- Bright outdoor light theme (sky blue, green grass, daylight)
- OpenGL lighting, fog, and smooth shading
- Particle effects on hits, kills, and power-up collection
- Translucent zone boundary wall
- Per-enemy health bars
- Damage flash overlay
- Shield visualization around player
- Tactical soldier player model (helmet, vest, rifle, backpack)

### 🗺️ HUD

- HP / Shield / Stamina bars
- Score & combo multiplier
- Level & kill progress
- Weapon indicator with ammo bar and slot display
- Active power-up timers
- Kill streak notifications
- Crosshair with hit markers (FP mode)
- Minimap (enemies, power-ups, zone, obstacles)
- Zone shrinking warnings

---

## Controls

### Movement

| Key            | Action                  |
| -------------- | ----------------------- |
| `W` / `S`      | Move forward / backward |
| `A` / `D`      | Rotate left / right     |
| `Q` / `E`      | Strafe left / right     |
| `Shift` + Move | Sprint (uses stamina)   |

### Combat

| Key         | Action                            |
| ----------- | --------------------------------- |
| `Space`     | Fire weapon                       |
| `1`/`2`/`3` | Switch weapon (Pistol/AR/Shotgun) |
| `R`         | Reload                            |

### Camera & System

| Key          | Action                     |
| ------------ | -------------------------- |
| `F`          | Toggle first/third person  |
| `Arrow Keys` | Zoom in/out (third person) |
| `P`          | Pause / Resume             |
| `R`          | Restart (when dead)        |
| `ESC`        | Quit game                  |

---

## Installation

### Prerequisites

- Python 3.7+
- pip

### Setup

```bash
git clone https://github.com/fnziad/target_frenzy_3D.git
cd target_frenzy_3D
pip install -r requirements.txt
```

### Run

```bash
python run_game.py
```

---

## Game Flow

1. **Name Entry** — Type your player name and press Enter
2. **Guidelines** — Review controls, enemies, and power-ups
3. **Battle** — Survive waves of enemies, collect power-ups, switch weapons
4. **Level Up** — Kill enough enemies to advance (+20 HP heal per level)
5. **Zone Shrinks** — After level 2, the zone closes in periodically
6. **Game Over** — Full stats screen (score, kills, streak, accuracy, time)
7. **Restart** — Press `R` to play again

---

## Project Structure

```
target_frenzy_3D/
├── src/
│   └── target_frenzy_3d.py     # Main game engine (2600+ lines)
├── run_game.py                  # Launcher with controls banner
├── requirements.txt             # PyOpenGL dependency
├── LICENSE                      # MIT License
├── README.md                    # This file
├── PROJECT_INFO.txt             # Detailed project info
└── .gitignore
```

---

## Technical Details

| Aspect            | Details                                                             |
| ----------------- | ------------------------------------------------------------------- |
| **Language**      | Python 3                                                            |
| **Graphics**      | OpenGL 2.x (fixed-function pipeline) via PyOpenGL + GLUT            |
| **Rendering**     | Custom 3D models from primitives (cubes, spheres, torus, octahedra) |
| **Physics**       | Momentum-based movement with friction; delta-time scaling           |
| **AI**            | 4 behavior patterns: chase, zigzag, maintain-distance, direct       |
| **Collision**     | Distance-based (spherical) and AABB for obstacles                   |
| **Frame Rate**    | 60 FPS target with sleep-based limiter                              |
| **Architecture**  | Single-file game engine with modular function design                |
| **Lines of Code** | ~2,600 lines of Python                                              |

---

## Author

**Fahad Nadim Ziad** — [@fnziad](https://github.com/fnziad)

Made with Python & OpenGL — 2026

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
