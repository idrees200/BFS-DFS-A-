# Maze Solving Algorithms

## Overview

This repository contains implementations of three classic pathfinding algorithms: Breadth-First Search (BFS), Depth-First Search (DFS), and A* Search. These algorithms are used to find paths from a start point (S) to a goal point (G) in a 2D grid maze. The maze is represented as a text file where '0' represents an open path, '1' represents a wall, 'S' is the start point, and 'G' is the goal point.

## Algorithms

### Breadth-First Search (BFS)

BFS explores the maze level by level, ensuring the shortest path is found. It uses a queue to manage nodes to be explored next. BFS is guaranteed to find the shortest path in an unweighted graph like our maze.

### Depth-First Search (DFS)

DFS explores as far as possible along each branch before backtracking. It uses a stack (implemented via recursion) to manage nodes. DFS is not guaranteed to find the shortest path but can be useful in scenarios where memory usage is a concern.

### A* Search

A* Search is an informed search algorithm that uses heuristics to guide its search. It combines the strengths of BFS (finding the shortest path) and heuristics (to improve efficiency). In this implementation, the Manhattan distance heuristic is used.

## Maze Representation

The maze is read from a text file where:
- '0' represents an open path
- '1' represents a wall
- 'S' represents the start point
- 'G' represents the goal point

### Example Maze (`cube.txt`)

0 0 1 0 S
1 0 1 0 0
0 0 0 0 1
0 1 1 0 G

## Usage

### Reading the Maze

The maze is read from a file using the `read_cube_from_file(filename)` function, which returns a 2D list representation of the maze.

### Finding Start and Goal Points

The start (`S`) and goal (`G`) points are located in the maze and their coordinates are stored in the `start` and `goal` variables, respectively.

### Pathfinding

Once the start and goal points are identified, you can find paths using the provided algorithms:

- **BFS**: `bfs(cube, start, goal)`
- **DFS**: `dfs(cube, start, goal, set(), [start])`
- **A***: `a_star(cube, start, goal)`

### Output

The program prints the input maze and the paths found by each algorithm. If no start or goal point is found, it indicates that as well.

## Example Output

Input Cube:
0 0 1 0 S
1 0 1 0 0
0 0 0 0 1
0 1 1 0 G

BFS Path: [(4, 0), (3, 0), (3, 1), (4, 1), (4, 2)]
DFS Path: [(4, 0), (3, 0), (3, 1), (4, 1), (4, 2)]
A* Path: [(4, 0), (3, 0), (3, 1), (4, 1), (4, 2)]
