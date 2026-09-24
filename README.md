# A* Maze Solver

An interactive **A* Pathfinding Algorithm Visualizer** built with **Python and PySide6**.

This project is designed to demonstrate how the A* algorithm searches for the shortest path between a **Start** and **Goal** while visually showing the search process. Users can create their own mazes, add or remove walls, watch the algorithm search step by step, and view detailed maze and search statistics.

---

## 🚀 Features

### 🧩 Interactive Maze Builder

* Create your own maze manually.
* Add and remove walls by clicking cells.
* Place or modify Start and Goal positions.
* Clear the maze and build a new one.
* Load a sample maze for testing.

### 🤖 A* Pathfinding

* Uses the A* search algorithm.
* Calculates the shortest path.
* Uses Manhattan distance as the heuristic.
* Supports four-directional movement:

  * Up
  * Down
  * Left
  * Right
* Diagonal movement is not allowed.

### 🎬 Step-by-Step Visualization

The application visually shows how A* searches through the maze.

| Symbol | Meaning               |
| ------ | --------------------- |
| `S`    | Start                 |
| `G`    | Goal                  |
| `C`    | Current Node          |
| `F`    | Frontier / Open Set   |
| `E`    | Explored / Closed Set |
| `P`    | Final Shortest Path   |
| `#`    | Wall                  |
| `.`    | Unexplored Cell       |

### 📊 Maze Information

The sidebar provides information about the current maze:

* Grid size
* Total cells
* Wall cells
* Open cells
* Start position
* Goal position

### 📈 A* Search Information

During and after the search, the application displays:

* Search status
* Current node
* Explored cells
* Frontier cells
* Shortest distance
* Path length
* Execution time
* `g(n)`, `h(n)`, and `f(n)` values when available

### 🚫 Blocked Maze Detection

If the Goal cannot be reached, the application clearly reports:

```text
Status: No Path Found

The goal is unreachable from the start.

Shortest Distance: N/A
Path Length: N/A
```

The application does not create or display a fake path.

### 🎮 Controls

* Solve Maze
* Pause
* Resume
* Reset
* Clear Maze
* Load Sample Maze
* Speed Control

---

# 🧠 How A* Works

A* combines the actual cost of reaching a node with an estimated cost of reaching the goal.

The main formula is:

```text
f(n) = g(n) + h(n)
```

Where:

```text
g(n) = Cost from Start to current node
h(n) = Estimated cost from current node to Goal
f(n) = Total estimated cost
```

This project uses the **Manhattan Distance** heuristic:

```text
h(n) = |current_row - goal_row| + |current_column - goal_column|
```

Because the application only allows movement in four directions, Manhattan distance is suitable for this grid.

---

# 📏 Shortest Distance vs Path Length

The application distinguishes between **shortest distance** and **path length**.

For example:

```text
S → A → B → C → G
```

There are:

```text
5 cells
4 movements
```

Therefore:

```text
Shortest Distance = 4
Path Length = 5 cells
```

For this project:

```text
Path Length = Shortest Distance + 1
```

when a path exists.

---

# 🗂️ Project Structure

```text
A Maze/
│
├── main.py
├── maze.py
├── astar.py
├── visualizer.py
│
├── ui/
│   ├── __init__.py
│   ├── main_window.py
│   └── maze_widget.py
│
├── test_maze.py
├── test_astar.py
├── test_ui.py
│
├── requirements.txt
└── README.md
```

> File names may change as the project evolves.

---

# 🛠️ Technologies Used

* **Python**
* **PySide6**
* **A* Search Algorithm**
* **Priority Queue / Heap**
* **Manhattan Distance**
* **Pytest**

---

# 💻 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Move into the project directory:

```bash
cd "A Maze"
```

## 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

## 3. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

If `requirements.txt` is not available:

```bash
pip install PySide6 pytest
```

---

# ▶️ Run the Application

Run:

```bash
python main.py
```

The PySide6 desktop application should open.

---

# 🧪 Run Tests

Run the complete test suite:

```bash
python -m pytest -q
```

You can also verify that all Python files compile correctly:

```bash
python -m compileall -q .
```

---

# 🖱️ How to Use

### 1. Build a Maze

Use the maze editor to create walls.

```text
S . . # . .
. # . # . .
. # . . . .
. . . # # .
# # . . . G
```

### 2. Set Start and Goal

The maze must contain:

```text
Exactly one Start
Exactly one Goal
```

### 3. Start A*

Click:

```text
Solve Maze
```

The algorithm will begin searching.

### 4. Watch the Search

The current node moves through the maze while A* evaluates possible routes.

You can see:

```text
C = Current
F = Frontier
E = Explored
```

### 5. View the Final Path

If a path exists, the shortest path is displayed as:

```text
P = Final Path
```

The sidebar will show the final statistics.

---

# 🚧 Blocked Maze Example

A maze may contain a Goal that cannot be reached:

```text
S . # . .
. . # . .
# # # # #
. . . . .
. . . . G
```

In this situation, A* explores all reachable cells and eventually determines that the Goal cannot be reached.

The result is:

```text
Status: No Path Found
Shortest Distance: N/A
Path Length: N/A
```

This demonstrates an important case in pathfinding: **not every Start and Goal combination has a valid path.**

---

# 📊 Example Result

For a reachable maze, an example result may look like:

```text
Status: Path Found

Start: (0, 0)
Goal: (4, 5)

Shortest Distance: 9
Path Length: 10 cells
Explored Cells: 18
Execution Time: 2.4 ms
```

The exact values depend on the maze and system performance.

---

# 🎯 Project Goals

This project was created to make the A* algorithm easier to understand by combining:

* Algorithm implementation
* Interactive maze creation
* Real-time visualization
* Step-by-step search
* Mathematical concepts
* Search statistics
* Desktop GUI development

Instead of only returning a path, the application shows **how A*** reaches its result.

---

# 🔮 Future Improvements

Possible future features include:

* Multiple heuristic options
* BFS comparison
* DFS comparison
* Dijkstra's algorithm comparison
* Weighted terrain
* Different movement costs
* Diagonal movement
* Random maze generation
* Maze generation algorithms
* Algorithm performance comparison
* Search history
* Export/import maze files
* Improved animation controls

---

# 👨‍💻 Author

**Muhammad Hamza**

Full Stack Developer & AI Developer

This project is part of my work in exploring **Artificial Intelligence, algorithms, Python development, and interactive visualization**.

---

## ⭐ Support

If you find this project useful or educational, consider giving the repository a ⭐ on GitHub.
