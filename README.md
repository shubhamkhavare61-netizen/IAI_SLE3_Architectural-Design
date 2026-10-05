# SLE-3: Architectural Design (Full C4 Model) - 4-Queens Solver (BFS vs DFS)

**Course:** 02AML204 - Introduction to Artificial Intelligence
**Name:** Shubham Khavare | **PRN:** 25UAM102 | **Division:** B

## About

This repository holds the SLE-3 architecture design for my 4-Queens Solver.
The system places 4 queens on a 4x4 board so that no two queens share a row, column or diagonal.
It solves the puzzle with two search strategies, **Breadth-First Search (BFS)** and **Depth-First Search (DFS)**, and compares them by nodes expanded and run time.

SLE-1 = Code, SLE-2 = Performance, **SLE-3 = Full Architecture Design.**

## C4 Model

### Level 1 - Context
The user gives N = 4 and chooses BFS or DFS. The system returns the queen positions, nodes expanded and run time. It depends only on the Python runtime (`time.perf_counter`, `matplotlib`).

![Level 1](docs/level1_context.png)

### Level 2 - Container
Five containers: Input Module, Search Engine, Constraint Checker, Profiler and Output Module.

![Level 2](docs/level2_container.png)

### Level 3 - Component (Search Engine)
Frontier (queue for BFS, stack for DFS), Goal Test, State Expander, Safety Filter and Solution Collector.

![Level 3](docs/level3_component.png)

### Level 4 - Code
Main functions only: `is_safe`, `goal_test`, `expand`, `bfs`, `dfs`, `profile_run`, `print_board` / `plot_chart`.

## Design Decisions

- Each container has one job (input, search, constraint check, measure, output).
- `is_safe()` is separate so BFS and DFS use the same rule, which keeps the comparison fair.
- BFS and DFS differ only in the Frontier (queue vs stack).
- The Profiler is separate so timing does not change the algorithm.

## Repository Contents

| File | Description |
|---|---|
| `README.md` | Project overview (this file) |
| `AI_CONTRIBUTION_LOG.md` | Honest record of AI help vs my own work |
| `SLE3_Architectural Design.docx` | Final SLE-3 report |
| `docs/` | The three C4 diagrams (PNG) |

## How to Run the Code

```bash
python main.py
```

(Use the main file name of your own code if different.)

## AI Use

See [AI_CONTRIBUTION_LOG.md](AI_CONTRIBUTION_LOG.md).
