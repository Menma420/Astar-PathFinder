# A* Path Finder 🚀

**A colorful, interactive A* pathfinding visualizer** written in Python + Pygame.
Place start/end, draw barriers, hit **Space** and watch A* explore the grid and reveal the shortest path

---

# Features ✨

* Real-time A* visualization (open set / closed set / final path)
* 50×50 default grid (configurable)
* Intuitive click controls for start / end / barriers
* Clean, single-file codebase — easy to extend
* Defensive neighbor checks so barriers aren’t accidentally traversed
* Lightweight and great for demos / teaching pathfinding concepts

---


### Screenshots

<img width="1005" height="1022" alt="image" src="https://github.com/user-attachments/assets/ad100e94-5ad5-4784-b821-1edf39dd2db6" />
<img width="1002" height="1023" alt="image" src="https://github.com/user-attachments/assets/e93b9621-2674-4213-a44c-fb885e16d4e9" />


# Quick Start (run locally) 🖥️

```bash
# clone
git clone https://github.com/your-username/astarfinder.git
cd astarfinder

# install pygame
pip install pygame

# run the visualiser
python main.py
```

---

# Controls — The Cheatsheet 🎮

* **Left Click**

  * 1st click: place **Start** (🟧 orange)
  * 2nd click: place **End** (🟦 turquoise)
  * subsequent clicks: place **Barriers** (⬛ black)
* **Right Click**

  * Reset clicked cell (clears start/end/barrier)
* **Space**

  * Run A*
* **C**

  * Clear grid (reset everything)
* **Window close**

  * Quit app

> The code currently uses `pygame.mouse.get_pressed()` — holding the left mouse will continuously paint. If you want single-click behaviour, switch to `MOUSEBUTTONDOWN` event handling.

---

# How it works (short + visual) 🧠

* `g(n)`: actual cost from start → current (uniform cost = 1 per move)
* `h(n)`: Manhattan distance (heuristic)
* `f(n) = g(n) + h(n)` — nodes expanded by lowest `f` first
* `came_from` is used for path reconstruction once the end is reached

---

# Code layout (single-file overview)

* `Node` — stores state, color helpers, draw logic, `update_neighbors`
* `h(p1,p2)` — heuristic (Manhattan)
* `algorithm(draw, grid, start, end)` — A* implementation (PriorityQueue)
* `reconstruct_path` — paints final path
* `main` — Pygame loop, event handling, and user controls

---

# Customization ideas (make it flashy) 🎨

* **Speed slider** — control visualization speed.
* **Diagonal movement** — 8-way neighbors + switch heuristic to Chebyshev/Euclidean.
* **Weighted tiles** — visualize Dijkstra / weighted A*.
* **UI overlay** — legend + controls + sliders using a simple UI lib or draw in Pygame.
* **Export/Load maps** — save grid states to JSON and load them.

---

# Roadmap 🗺️

* [x] Basic A* working (4-direction)
* [x] Defensive neighbor checks & color fixes
* [ ] Add more algorithms
* [ ] Add speed control
* [ ] Add zooming

---

# Contributing 🤝

1. Fork the repo
2. `git checkout -b feature/awesome`
3. Make changes & test locally
4. `git commit -am "Add flashy feature"`
5. Open a PR — include screenshots/GIFs of changes

If you want, I can open a PR that:

* switches to single-click placement (`MOUSEBUTTONDOWN`), **or**
* adds diagonal movement and toggles, **or**
* adds a simple UI legend overlay with keys & colors

Tell me which and I’ll prepare the patch.

---


# Credits & Acknowledgements

Made with ❤️ using Pygame. Inspired by many A* tutorial visualizers and educational resources.

---
