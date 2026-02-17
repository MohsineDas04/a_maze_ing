# **A-Maze-Ing 🌽**

**A-Maze-Ing** is a sophisticated terminal-based maze generator and solver. It visualizes the creation of mazes using algorithms like **Recursive Backtracking** and **Prim's Algorithm**, and solves them using **Breadth-First Search (BFS)**.

This project was built to explore algorithmic complexity, Python package structure, and ANSI terminal manipulation without external GUI libraries.

## **📸 Features**

* **🧠 Algorithms:**  
  * **Recursive Backtracking (DFS):** Generates long, winding corridors ("river" style).  
  * **Prim's Algorithm:** Generates a more branching structure with many short dead ends.  
  * **Breadth-First Search (BFS):** Guarantees the shortest path solution.  
* **🎨 Visualization:**  
  * Real-time animated generation in the terminal.  
  * Custom "42" pattern embedded in the maze walls.  
  * Interactive menu to change colors, toggle solutions, and regenerate on the fly.  
* **⚙️ Configurable:**  
  * Adjustable dimensions (Width/Height).  
  * Custom Entry/Exit points.  
  * **Perfect vs. Imperfect Mazes:** Option to break walls randomly to create loops.  
  * **Seed Support:** Reproducible maze generation.

## **🚀 Installation & Setup**

### **Prerequisites**

* Python 3.10 or higher.  
* pip (Python Package Installer).

### **Automated Install (Recommended)**

We have provided a Makefile to handle dependencies automatically.

\# Clone the repository  
git clone https://github.com/MohsineDas04/a_maze_ing.git

\# Install dependencies  
make install

### **Manual Install**

If you prefer not to use Make:

pip install \--upgrade pip  
pip install flake8 mypy build

## **🎮 Usage**

### **Running the Generator**

To launch the visualizer with the default configuration:

make run

*Or manually:*

python3 a\_maze\_ing.py config.txt

### **Interactive Controls**

Once the maze is generated and solved, the terminal will display an interactive menu:

| Key | Action |
| :---- | :---- |
| **1** | **Re-generate:** Create a new maze with current settings. |
| **2** | **Toggle Path:** Show/Hide the BFS solution path. |
| **3** | **Wall Colors:** Cycle through ANSI colors for walls. |
| **4** | **Pattern Color:** Change the color of the "42" pattern. |
| **5** | **Switch Algorithm:** Toggle between Backtracking and Prim's. |
| **q** | **Quit:** Save the maze to file and exit. |

## **📝 Configuration (config.txt)**

You can modify config.txt to change the maze parameters without touching the code.

WIDTH=15            \# Width of the maze grid  
HEIGHT=14           \# Height of the maze grid  
ENTRY=0,0           \# Starting coordinate (x,y)  
EXIT=14,13          \# Ending coordinate (x,y)  
OUTPUT\_FILE=maze.txt \# File to save the hex representation  
PERFECT=True        \# True \= One solution; False \= Loops allowed  
SEED=12345          \# (Optional) Integer for reproducible mazes

## **🧪 Testing & Code Quality**

This project adheres to strict coding standards. We used **Flake8** for style enforcement and **MyPy** for static type checking.

### **How to Test**

To run the full suite of linters and type checkers:

make lint

For strict type checking (no untyped definitions allowed):

make lint-strict

### **Clean Up**

To remove cached files (\_\_pycache\_\_, .mypy\_cache, etc.):

make clean

## **🧠 What We Learned**

Developing **A-Maze-Ing** provided deep insights into several key areas of software engineering:

### **1\. Algorithmic Logic**

* **DFS vs. Prim's:** We learned the visual and structural differences between depth-first generation (stack-based, long paths) and Prim's (frontier-based, random selection).  
* **Graph Traversal:** Implementing BFS taught us how to use queues (deque) to track visited nodes and reconstruct the shortest path by backtracking from the destination to the source.

### **2\. Python Architecture**

* **Packaging:** We structured the project as a proper Python package (mazegen), separating the reusable core logic from the execution script (a\_maze\_ing.py).  
* **Type Hinting:** We utilized Python's typing module (List, Tuple, Optional, Set) to ensure type safety, making the code self-documenting and reducing runtime errors.

### **3\. Terminal Manipulation**

* **ANSI Escape Codes:** Instead of relying on heavy libraries like curses or pygame, we learned to manipulate the terminal cursor and colors directly using raw ANSI strings. This keeps the project lightweight and dependency-free.

## **👥 Authors**

* **rhssayn** \- *UX, Pathfinding, Interactive Menu, "42" Pattern*  
* **mlakhlil** \- *Core Algorithmic Logic (Backtracking & Prim's), Grid Visualization*

## **📄 License**

This project is licensed under the MIT License \- see the LICENSE file for details.
