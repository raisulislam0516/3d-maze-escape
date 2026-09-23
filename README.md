[README (2).md](https://github.com/user-attachments/files/32566913/README.2.md)
# 3D Maze Escape & Gem Collector

A 3D maze-escape survival game built entirely with **Python + PyOpenGL/GLUT** (legacy fixed-function OpenGL, no external game engine). Explore a procedurally-generated hedge maze, collect gems and keys, dodge environmental traps, and fight off enemy soldiers — all before the timer runs out.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![PyOpenGL](https://img.shields.io/badge/PyOpenGL-GLUT-green)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## Features

- **Procedural 3D maze** — a new hedge-maze layout every time, generated with a recursive-backtracker algorithm
- **Glowing spinning gems** — collect them for score, chain pickups for combo bonuses
- **Dual camera view** — switch between First-Person and Overhead views
- **Key & locked exit door** — find all 3 keys scattered in the maze to unlock the exit
- **Environmental traps**
  - Swinging pendulum blades
  - Timed laser gates (with a warning flash before they activate)
  - Hidden floor spike traps
- **Combat system**
  - Player has a gun (left-click to shoot)
  - 3 enemy soldier types: **Pistol** (1-hit kill), **Assault** (armored, 3–4 hits), **Shotgun** (throws grenades)
  - Soldiers patrol, detect the player via line-of-sight, and strafe/move while engaging in combat
- **Live HUD** — health, countdown timer, gem/key/soldier counters, score, exit compass, and a mini-map
- **God Mode cheat** — toggle invincibility and no-clip for testing or fun
- **Garden hedge-maze visual theme** — green hedges, grassy floor, open sky

---

## Controls

| Key / Input | Action |
|---|---|
| `W` / `S` | Move forward / backward |
| `A` / `D` | Turn left / right |
| **Left Mouse Click** | Fire gun |
| `V` | Toggle camera view (First-Person / Overhead) |
| `C` | Toggle God Mode (invincible, no-clip) |
| `R` | Reset game (generates a new maze) |

---

## Objective

1. Collect the **3 keys** hidden around the maze to unlock the exit door
2. Grab **gems** along the way for score (chain pickups quickly for combo bonuses)
3. Avoid or fight through **traps and enemy soldiers**
4. Reach the exit before the timer runs out and before your health hits zero

---

## Installation & Running

**Requirements:** Python 3.x, PyOpenGL

```bash
pip install PyOpenGL PyOpenGL_accelerate
```

> **Windows users:** if you get a GLUT-related error, you may also need `freeglut.dll` available on your system (place it alongside your Python executable or in `System32`).

**Run the game:**

```bash
python maze_escape.py
```

---

## Project Structure

```
maze_escape.py     # entire game (maze generation, rendering, combat, HUD) — single file
README.md
```

---

## Tech Notes

- Built using only `OpenGL.GL`, `OpenGL.GLUT`, `OpenGL.GLU`, plus Python's standard `math`, `random`, and `time` modules — no external game engine or assets
- Uses immediate-mode OpenGL rendering (`glBegin`/`glEnd`, `glutSolidCube`, `gluSphere`, `gluCylinder`) — no shaders or textures
- Maze generated via a recursive-backtracker algorithm
- Simple AABB-based collision detection for walls, doors, and entities

---

## License

This project is open-sourced under the MIT License — feel free to fork, modify, and build on it.
