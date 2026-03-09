# 📖 Graph Theory Project Explanation

## 1. Trees

A **tree** is an undirected, connected, acyclic graph. For `n` vertices it has exactly `n − 1` edges, and there is a unique path between every pair of nodes.

A **rooted tree** designates one node as the root; every other node has exactly one parent. In this project the university campus is the root and its sub-locations (blocks, rooms, facilities) form the children, creating a natural hierarchy.

---

## 2. Tree Traversals

Traversals visit every node in a tree exactly once. The four standard methods are:

| Traversal | Strategy | Key Idea |
|-----------|----------|----------|
| **Pre-Order** | NLR | Visit the node *before* its children. Useful for copying a tree. |
| **In-Order** | LNR | Visit the left subtree, then the node, then the right subtree (extended for general trees by visiting the first child, then the node, then remaining children). Produces sorted order for BSTs. |
| **Post-Order** | LRN | Visit all children *before* the node. Useful for safe deletion or evaluating expressions. |
| **Level-Order** | BFS | Visit nodes level by level using a **queue**. Equivalent to Breadth-First Search. |

Pre-Order, In-Order, and Post-Order are depth-first strategies; Level-Order is a breadth-first strategy.

---

## 3. Spanning Trees

A **spanning tree** of a connected graph `G = (V, E)` is a subgraph that:
- Contains **all** vertices of `G`
- Is connected and acyclic (i.e., is a tree)
- Has exactly `|V| − 1` edges

Two classical construction methods:

- **DFS Spanning Tree** — Run a Depth-First Search from any start vertex; the discovery edges form a spanning tree.
- **BFS Spanning Tree** — Run a Breadth-First Search from any start vertex; the discovery edges form a spanning tree.

Different starting vertices or different ordering of neighbors can yield different spanning trees for the same graph.

---

## 4. Minimum Spanning Tree (MST)

For a **weighted**, connected graph, a Minimum Spanning Tree is the spanning tree whose **total edge weight is minimized**. Two classical greedy algorithms solve this:

### Kruskal's Algorithm
1. Sort all edges by weight (ascending).
2. For each edge (lightest first): add it to the MST **if** it does not form a cycle.
3. Stop when `|V| − 1` edges have been added.

Cycle detection is done efficiently using **Union-Find** (see below). Time complexity: **O(E log E)**.

### Prim's Algorithm
1. Start from an arbitrary vertex; mark it as *visited*.
2. Among all edges connecting a visited vertex to an unvisited vertex, pick the one with the **smallest weight**.
3. Add that edge and mark the new vertex as visited.
4. Repeat until all vertices are visited.

Time complexity: **O(E log V)** with a binary heap / priority queue.

Both algorithms are guaranteed to produce an optimal MST by the **cut property**: for any cut of the graph, the minimum-weight crossing edge must belong to some MST.

---

## 5. Dijkstra's Algorithm (Shortest Path)

**Dijkstra's Algorithm** computes the shortest path from a single source to all other vertices in a graph with **non-negative** edge weights.

### Steps
1. Set `dist[source] = 0` and `dist[v] = ∞` for all other vertices.
2. Insert all vertices into a **min-priority queue** keyed by distance.
3. Extract the vertex `u` with the smallest `dist` value.
4. For each neighbor `v` of `u`: if `dist[u] + weight(u, v) < dist[v]`, update `dist[v]` (relaxation) and record `u` as the predecessor of `v`.
5. Repeat until the queue is empty or the target vertex is extracted.

The predecessor chain gives the actual shortest path. Time complexity: **O((V + E) log V)** with a binary heap.

> **Limitation:** Dijkstra's does not work correctly with negative edge weights. For graphs with negative weights, use the Bellman-Ford algorithm instead.

---

## 6. Union-Find (Disjoint Set Union)

The **Union-Find** data structure maintains a collection of disjoint sets and supports two operations:

- **Find(x)** — Returns the representative (root) of the set containing `x`. Uses **path compression** to flatten the tree structure for future queries.
- **Union(x, y)** — Merges the sets containing `x` and `y`. Uses **union by rank** to keep trees balanced.

With both optimizations the amortized time per operation is nearly **O(1)** — formally **O(α(n))**, where α is the inverse Ackermann function.

In this project, Union-Find is used inside **Kruskal's Algorithm** to efficiently determine whether adding an edge would create a cycle.

---

## References

- Cormen, Leiserson, Rivest, Stein — *Introduction to Algorithms* (CLRS)
- Diestel — *Graph Theory*
- Sedgewick, Wayne — *Algorithms* (4th Edition)
