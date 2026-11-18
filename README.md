# Kruskal's Algorithm (Minimum Spanning Tree): Implementation & Time Analysis

A Jupyter notebook implementing and analyzing **Kruskal's algorithm** in Python to find the **Minimum Spanning Tree (MST)** of a weighted, undirected graph.

## Features
- **Union-Find (Disjoint Set Union)** with path compression and union by rank for fast cycle detection
- Kruskal's algorithm with a step-by-step log showing every edge as accepted or rejected (and why)
- Interactive user input for custom weighted edges
- Real runtime measurement using Python's `time` module
- Time and space complexity analysis
- Graph visualization with the MST highlighted (via `networkx` / `matplotlib`)
- Verification of results against `networkx`'s built-in MST
- Demo of a **minimum spanning forest** on a disconnected graph
- Runtime comparison of Kruskal's vs heap-based Prim's on **sparse** and **dense** random graphs, with charts

## Getting Started
1. Clone the repo
2. Install dependencies: `pip install jupyter matplotlib networkx`
3. Open `kruskals_algorithm_analysis.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab
4. Run the cells top to bottom — the demo cell uses a sample graph by default; swap in `get_user_edges()` (no arguments) to enter your own graph

## Complexity Summary

| Algorithm         | Time Complexity          | Space Complexity | Key Data Structure             | Disconnected Graphs?                  |
|---------------------|----------------------------|---------------------|----------------------------------|-----------------------------------------|
| Kruskal's           | O(E log E) = O(E log V)    | O(V + E)             | Sorted edge list + Union-Find    | Yes (minimum spanning forest)           |
| Prim's (min-heap)   | O(E log V)                 | O(V + E)             | Min-heap                         | Only the start vertex's component       |

Where `V` = number of vertices, `E` = number of edges.

Kruskal's is a **greedy** algorithm that repeatedly adds the cheapest edge that does not form a cycle, merging separate components until `V − 1` edges are chosen. The sorting step dominates the running time. In the notebook's experiment, Kruskal's was faster than heap-based Prim's on both sparse and dense random graphs; results depend on the implementation and language.

## License
MIT
