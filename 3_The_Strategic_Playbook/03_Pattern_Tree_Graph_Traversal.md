---
markmap:
  colorScheme: 'teal'
---

# The Playbook: Tree & Graph Traversal

## 🌊 Breadth-First Search (BFS)
- **Core Idea:** Explores level by level. It visits all the direct neighbors of a node before moving on to their neighbors.
- **Analogy:** The ripples spreading out from a stone dropped in a pond.
- **Key Data Structure:** **Queue** (FIFO - First-In, First-Out). This is essential to process nodes in the order they are discovered.
- **When to Use It?**
  - **Finding the Shortest Path** in an **unweighted** graph or tree.
  - **Level-Order Traversal:** Processing a tree one level at a time.
  - Any problem that involves finding something "closest" or "minimum number of steps."
- **The Game Plan (Iterative Template):**
  ```
  function bfs(startNode):
    queue = new Queue()
    visited = new Set()

    queue.enqueue(startNode)
    visited.add(startNode)

    while queue is not empty:
      currentNode = queue.dequeue()
      // Process currentNode here

      for each neighbor of currentNode:
        if neighbor is not in visited:
          visited.add(neighbor)
          queue.enqueue(neighbor)
  ```
- **Classic Blueprints:**
  - [Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)
  - [Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/)
  - [Number of Islands](https://leetcode.com/problems/number-of-islands/) (A classic graph problem)

## 🌲 Depth-First Search (DFS)
- **Core Idea:** Goes as deep as possible down one path before backtracking and trying another.
- **Analogy:** Navigating a maze by following one path to its end, then backtracking to the last junction to try a different turn.
- **Key Data Structure:** **Stack** (LIFO) for an iterative approach, or the **Call Stack** for a more intuitive **recursive** approach.
- **When to Use It?**
  - **Checking if a path exists** between two nodes.
  - **Exploring all possible paths** (e.g., finding all permutations/combinations, solving mazes).
  - **Detecting cycles** in a graph.
  - **Topological Sorting.**
- **The Game Plan (Recursive Template):**
  ```
  function dfs(currentNode, visited):
    // Process currentNode here
    visited.add(currentNode)

    for each neighbor of currentNode:
      if neighbor is not in visited:
        dfs(neighbor, visited)
  ```
- **Classic Blueprints:**
  - [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
  - [Path Sum](https://leetcode.com/problems/path-sum/)
  - [Number of Connected Components](https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/)

## BFS vs. DFS: The Quick Summary
- **BFS:** Wider, shallower. Finds the shortest path. Uses a Queue.
- **DFS:** Deeper, narrower. Explores all possibilities. Uses a Stack or Recursion.

