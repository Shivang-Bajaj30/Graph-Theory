# Graph Theory Explorer: CHRIST University Delhi NCR

This interactive web application demonstrates core theoretical concepts of Graph Theory by applying them to an accurate model of the **CHRIST (Deemed to be University) Delhi NCR campus**. 

Graph Theory is the mathematical study of graphs, which are mathematical structures used to model pairwise relations between objects. A graph is made up of vertices (also called nodes or points) which are connected by edges (also called links or lines).

## Theoretical Foundation

The application models the geographical and logical layout of the campus using fundamental mathematical and data structures:

*   **Vertices (Nodes) $V$:** In our model, $V$ represents the set of key campus landmarks (e.g., Block A, Block B, Central Lawn, Main Turf). Internal spaces such as classrooms, libraries, and offices are modeled as sub-vertices within a hierarchical structure. Mathematically, a graph $G$ is an ordered pair $G = (V, E)$.
*   **Edges $E$:** $E$ represents the set of physical paths and walkways connecting the landmarks $V$. An edge $e \in E$ is a 2-element subset of $V$, typically denoted as $e = \{u, v\}$ where $u, v \in V$.
*   **Weighted Edges:** Our graph is a **Weighted Graph**. Each edge $e$ has an associated weight or cost, $w(e)$, representing the estimated physical walking distance in meters (e.g., $w(\{Central Lawn, Block B\}) = 30m$). This allows for quantitative analysis of paths.
*   **Hierarchical Trees (Arborescence):** A tree is a connected acyclic undirected graph. The campus is grouped sequentially into a unified parent-tree structure (Overall Campus ➔ Key Blocks/Hubs ➔ Specific Internal Facilities). This reflects a specific type of directed graph called an arborescence (or a rooted directed tree), where there is exactly one path from a designated root node (the overall campus) to any other node.

## Core Theoretical Concepts Demonstrated

### 1. Tree Traversals
Graph traversal (or graph search) refers to the process of visiting (checking and/or updating) each vertex in a graph. For tree structures, traversals systematically visit nodes.
*   **Pre-order (NLR - Node, Left, Right):** Visits the current node, then traverses the left subtree, then the right subtree. Useful for creating a copy of the tree.
*   **In-order (LNR - Left, Node, Right):** Traverses the left subtree, visits the node, then traverses the right subtree. In a Binary Search Tree, this yields elements in sorted order.
*   **Post-order (LRN - Left, Right, Node):** Traverses the left subtree, then the right subtree, then visits the node. Useful for deleting a tree from leaf to root.
*   **Level-order (Breadth-First Traversal):** Visits nodes level by level, from left to right. It uses a queue data structure.

### 2. Spanning Trees (Graph Traversal Algorithms)
A spanning tree $T$ of a connected, undirected graph $G$ is a subgraph that is a tree and includes all of the vertices of $G$. The application demonstrates finding spanning trees using two fundamental algorithms:
*   **Breadth-First Search (BFS):** Explores the graph layer by layer, expanding outward from the starting vertex. It finds the shortest path (in terms of the number of edges) from the root vertex to all other vertices.
*   **Depth-First Search (DFS):** Explores as far as possible along each branch before backtracking. It creates a deep, narrow spanning tree.

### 3. Minimum Spanning Tree (MST)
For a weighted, connected, undirected graph, a Minimum Spanning Tree is a spanning tree with weight less than or equal to the weight of every other spanning tree. The weight of a spanning tree is the sum of weights given to each edge of the spanning tree. It is used to find the most cost-effective way to connect all vertices (e.g., laying fiber optic cable across campus hubs).
*   **Kruskal's Algorithm:** A greedy algorithm that finds an MST for a connected weighted graph. It works by sorting all the edges in non-decreasing order of their weight and iteratively adding the smallest edge to the forest, provided it doesn't form a cycle (checked using a Disjoint-Set / Union-Find data structure).
*   **Prim's Algorithm:** Another greedy algorithm that finds an MST. It starts with an arbitrary vertex and iteratively adds the minimum weight edge that connects a vertex in the tree to a vertex outside the tree, growing the tree one vertex at a time.

### 4. Shortest Path (Dijkstra's Algorithm)
The shortest path problem is the problem of finding a path between two vertices (or nodes) in a graph such that the sum of the weights of its constituent edges is minimized.
*   **Dijkstra's Algorithm:** Calculates the shortest paths from a single source vertex to all other vertices in a graph with non-negative edge weights. It maintains a set of unvisited vertices and iteratively selects the unvisited vertex with the smallest tentative distance, updating the distances of its neighbors. This acts as a functional navigation system (e.g., the fastest walking route from Synergy Square to Domino's).

## Why the Christ Campus?

By grounding profound theoretical mathematical concepts—vertices, edges, subgraphs, traversals, and optimization algorithms—in the tangible, geographical layout of the **CHRIST Delhi NCR campus**, the abstract framework of Graph Theory becomes highly intuitive. 

Solving abstract problems like "minimizing the total weight of a spanning tree $T \subseteq G$" is translated into relatable scenarios like "finding the most efficient way to lay network cables across all major university blocks." This contextualization makes the mathematics behind data structures and algorithms far more accessible.
