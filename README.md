# 🌳 Graph Theory Explorer

An interactive web application for visualizing Graph Theory concepts, modeled on the **CHRIST (Deemed to be University) — Delhi NCR Campus**. Built with **React** and **Vite**.

---

## Prerequisites

- **Node.js** (v18 or later)
- **npm**

## Installation

```bash
git clone https://github.com/Shivang-Bajaj30/Graph-Theory.git
cd Graph-Theory
npm install
```

## Run Locally

```bash
npm run dev
```

Open `http://localhost:5173` in your browser.

## Production Build

```bash
npm run build
npm run preview
```

## Project Structure

```
src/
├── App.jsx                 # Tab navigation & layout
├── main.jsx                # React entry point
├── index.css               # Global styles
├── data/
│   └── campusData.js       # Campus graph data & algorithm implementations
└── components/
    ├── CampusTree.jsx          # Interactive tree visualization
    ├── TreeTraversals.jsx      # Animated traversal demos
    ├── SpanningTree.jsx        # DFS / BFS spanning trees
    ├── MinSpanningTree.jsx     # Kruskal's & Prim's MST
    └── DistanceCalculator.jsx  # Dijkstra shortest path
```

## Tech Stack

| Layer    | Technology   |
| -------- | ------------ |
| Frontend | React 19     |
| Bundler  | Vite 7       |
| Graphics | SVG (inline) |
| Styling  | Vanilla CSS  |
| Linting  | ESLint       |
