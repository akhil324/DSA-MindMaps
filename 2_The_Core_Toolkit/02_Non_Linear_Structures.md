---
markmap:
  colorScheme: 'indigo'
---

# The Core Toolkit: Non-Linear Structures

## 🔑 Hash Tables (Hash Maps / Dictionaries)
- **Core Idea:** A structure that maps **keys** to **values** for super-fast lookups. Like a real-world dictionary where the "key" is the word and the "value" is its definition.
- **How it Works:**
  1. A `hash function` converts the key into an array index.
  2. The value is stored at that index.
- **Pros:**
  - **Extremely Fast (Average O(1)):** Lookups, insertions, and deletions are, on average, constant time.
- **Cons:**
  - **Unordered:** The data is not stored in any particular order.
  - **Hash Collisions:** Two different keys might map to the same index. This is handled internally but can degrade performance to O(n) in the worst case.
- **Operations & Big O (Average Case):**
  - `Insert`: O(1)
  - `Delete`: O(1)
  - `Search (by key)`: O(1)
- **Key Use Cases:**
  - **Caching:** Storing frequently accessed data.
  - **Counting Frequencies:** (e.g., "Two Sum" problem, finding duplicates).
  - The backbone of many programming language objects/dictionaries.

## 🌳 Trees
- **Core Idea:** A hierarchical structure with a **root** node and child nodes. Like a family tree or a file system directory.
- **Key Terminology:**
  - `Root`: The top-most node.
  - `Parent / Child`: A node directly connected to another node when moving away from the Root.
  - `Leaf`: A node with no children.
  - `Depth / Height`: Levels of the tree.
- **Common Types:**
  - **Binary Tree (BT):** Each node has at most **two** children (left and right).
  - **Binary Search Tree (BST):** A special BT where for any node:
    - All left children have smaller values.
    - All right children have larger values.
    - This property makes searching very efficient (O(log n)).
- **Key Algorithms & Patterns:**
  - **Tree Traversal (BFS & DFS):** The fundamental way to navigate and process trees.

## ⛰️ Heaps
- **Core Idea:** A special tree-based structure that satisfies the "heap property." Primarily used for implementing **Priority Queues**.
- **Types:**
  - **Min-Heap:** The parent node is always **smaller** than its children. The smallest element is always at the root.
  - **Max-Heap:** The parent node is always **larger** than its children. The largest element is always at the root.
- **Operations & Big O:**
  - `Insert`: O(log n)
  - `Get Min/Max`: O(1)
  - `Delete Min/Max`: O(log n)
- **Key Use Cases:**
  - **Priority Queues:** Efficiently getting the highest or lowest priority item.
  - **The "Top K Elements" Pattern:** Finding the k-largest or k-smallest items in a collection.
  - **Heap Sort Algorithm.**

## 🌐 Graphs
- **Core Idea:** A collection of **nodes (vertices)** connected by **edges**. The ultimate structure for representing networks.
- **Analogy:** A social network (people are nodes, friendships are edges) or a map (cities are nodes, roads are edges).
- **Types:**
  - **Directed:** Edges have a direction (like a one-way street).
  - **Undirected:** Edges have no direction (like a two-way street).
  - **Weighted:** Edges have a "cost" or "weight" (like the distance between cities).
  - **Unweighted:** Edges are all equal.
- **Representations:**
  - **Adjacency List:** Most common and efficient. A map of each node to a list of its neighbors.
  - **Adjacency Matrix:** A 2D grid, good for dense graphs.
- **Key Algorithms & Patterns:**
  - **Graph Traversal (BFS & DFS):** Finding paths, detecting cycles.
  - **Topological Sort:** Ordering nodes with dependencies.
  - **Shortest Path Algorithms:** (e.g., Dijkstra's, Bellman-Ford).

