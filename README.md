# ADS-4-assignment
Graph Toolkit: BFS and DFS Implementation
This project is a complete C++ graph toolkit designed for the Iot-2402 (Algorithms and Data Structures) course. It provides a robust Graph ADT using an adjacency list representation and implements core traversal algorithms (BFS and DFS) to solve pathfinding and cycle detection problems.


Features
Graph ADT: Supports directed/undirected modes and weighted/unweighted edges.
Representations: Primary storage in an Adjacency List with a built-in exporter for Adjacency Matrix.
BFS: Computes traversal order, distances, and parents for shortest path reconstruction.
DFS: Includes both Recursive and Iterative (stack-based) variants.
Applied Problem: Solves "Dependency Safety" (cycle detection in directed graphs).

How to Run
The program is designed to be run from the command line without manual setup steps.

1. Build
If using C++:
g++ -o graph_tool main.cpp

2. Execution (Scenarios)
The program supports input via Edge List or Adjacency List formats.
Scenario A: Shortest Path (BFS)
To find the shortest path between two nodes:
java Main --bfs input.txt start_node target_node

Scenario B: Dependency Safety (DFS) 
To check for cycles in a dependency graph:
java Main --check-cycles dependencies.txt

Input Format Specification
The program follows the assignment's input requirements:

Edge List Format (n m directed weighted):

6 7 0 0    # 6 vertices, 7 edges, undirected (0), unweighted (0)
0 1        # Edge between 0 and 1
0 2
1 3
...


Neighbor Ordering (Traversals)
To ensure the output is deterministic, the toolkit follows these rules:
Storage: When an edge is added, neighbors are stored in a list.
Sorting: Before any traversal (BFS or DFS) begins, the neighbor list for the current vertex is sorted in ascending order.
Result: This guarantees that if vertex 0 is connected to 2 and 1, the algorithms will always visit 1 before 2.

Complexity Summary
As analyzed in the report:
BFS/DFS (Adjacency List): Time O(∣V∣+∣E∣), Space O(∣V∣)
BFS/DFS (Adjacency Matrix): Time O(∣V∣ˆ2), Space O(∣V∣ˆ2)


Testing
The project includes a test suite covering:
Empty and single-vertex graphs.
Disconnected components.
Cycle detection accuracy.
BFS shortest path correctness.
