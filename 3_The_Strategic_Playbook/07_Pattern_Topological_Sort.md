---
markmap:
  colorScheme: 'indigo'
---

# The Playbook: Topological Sort

## 💡 The Big Idea
- An algorithm for ordering the nodes in a **Directed Acyclic Graph (DAG)**.
- It produces a linear ordering of nodes such that for every directed edge from node `u` to node `v`, node `u` comes before node `v` in the ordering.
- **Core Idea:** You can't take a course until you've completed its prerequisites. Topological Sort gives you a valid sequence to take the courses.

## 🔍 When to Use It? (Problem Clues)
- The problem involves **dependencies**, **prerequisites**, or a specific **order of tasks**.
- The underlying structure is a **Directed Acyclic Graph (DAG)**. If the graph has a cycle, a topological sort is not possible.
- You are asked to find a "valid sequence," "order of compilation," or "course schedule."

## 🛠️ The Game Plan: Kahn's Algorithm (BFS-based)
- This is the most common and intuitive way to perform a topological sort.
- **Core Data Structures:**
  - A **Queue** to store nodes with no incoming edges.
  - An **in-degree map/array** to count how many incoming edges each node has.

## ⚙️ The Algorithm Steps
1.  **Build the Graph & In-Degrees:**
    - Create an adjacency list to represent the graph.
    - Create an in-degree map/array. For each edge `u -> v`, increment the in-degree of `v`.

2.  **Find the Sources:**
    - Iterate through all nodes in the graph.
    - Add any node with an in-degree of `0` to the queue. These are your starting points (tasks with no prerequisites).

3.  **Process the Queue:**
    - Initialize an empty list for the sorted order.
    - While the queue is not empty:
      - Dequeue a node and add it to your sorted list.
      - For each of the dequeued node's neighbors:
        - Decrement their in-degree by 1 (since we've "completed" the prerequisite task).
        - If a neighbor's in-degree becomes `0`, add it to the queue.

4.  **Check for Cycles:**
    - After the loop, if the size of your sorted list is equal to the total number of nodes, you have a valid topological sort.
    - If the size is smaller, it means there was a cycle in the graph, and it was impossible to process all nodes.

## 经典蓝图 (Classic Blueprints)
- **Medium:**
  - [Course Schedule](https://leetcode.com/problems/course-schedule/) (Detecting if a sort is possible)
  - [Course Schedule II](https://leetcode.com/problems/course-schedule-ii/) (Actually producing the sorted order)
- **Hard:**
  - [Alien Dictionary](https://leetcode.com/problems/alien-dictionary/)
  - [Sequence Reconstruction](https://leetcode.com/problems/sequence-reconstruction/)
