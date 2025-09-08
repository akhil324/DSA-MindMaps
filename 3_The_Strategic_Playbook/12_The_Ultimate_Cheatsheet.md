

# The Playbook: The Ultimate Cheatsheet

## 🏛️ Data Structures: Quick Facts

- **Array**
  - **Access:** O(1)
  - **Search:** O(n)
  - **Insert/Delete:** O(n)
  - **Use For:** Fast access by index.
- **Linked List**
  - **Access/Search:** O(n)
  - **Insert/Delete (at ends):** O(1)
  - **Use For:** Dynamic size, fast insertions/deletions.
- **Stack (LIFO)**
  - **Push/Pop/Peek:** O(1)
  - **Use For:** Reversing, function calls, balanced parens.
- **Queue (FIFO)**
  - **Enqueue/Dequeue/Peek:** O(1)
  - **Use For:** BFS, task scheduling.
- **Hash Table**
  - **Insert/Delete/Search:** O(1) avg
  - **Use For:** Fast lookups, counting frequencies.
- **Binary Search Tree (BST)**
  - **Insert/Delete/Search:** O(log n) avg
  - **Use For:** Keeping data sorted for fast lookups.
- **Heap (Priority Queue)**
  - **Insert/Delete-Top:** O(log n)
  - **Get-Top:** O(1)
  - **Use For:** Finding min/max, Top K problems.
- **Graph**
  - **Use For:** Modeling networks, dependencies.
  - **Traversal:** BFS (shortest path), DFS (explore all paths).

## 📖 Strategic Patterns: Problem Clues

- **Sliding Window**
  - **Clue:** "contiguous subarray/substring", "longest/shortest", "fixed size k"
  - **Complexity:** O(n)
- **Two Pointers**
  - **Clue:** **Sorted** array, find a pair/triplet, palindrome check.
  - **Complexity:** O(n)
- **Fast & Slow Pointers**
  - **Clue:** **Linked List** cycle, middle node, k-th from end.
  - **Complexity:** O(n)
- **Tree/Graph BFS**
  - **Clue:** "shortest path", "level-order", "minimum steps".
  - **Complexity:** O(V+E)
- **Tree/Graph DFS**
  - **Clue:** "find if path exists", "all possible paths", cycle detection.
  - **Complexity:** O(V+E)
- **Top K Elements**
  - **Clue:** "top/k-th largest/smallest/frequent".
  - **Complexity:** O(n log k)
- **Subsets / Backtracking**
  - **Clue:** "all possible subsets/permutations/combinations".
  - **Complexity:** Often exponential (e.g., O(2ⁿ * n))
- **Dynamic Programming**
  - **Clue:** "max/min value", "number of ways", overlapping subproblems.
  - **Complexity:** Varies (e.g., O(n*m))
- **Topological Sort**
  - **Clue:** **Dependencies**, "prerequisites", "course schedule", DAG.
  - **Complexity:** O(V+E)
- **Modified Binary Search**
  - **Clue:** **Rotated** sorted array, search on the answer space.
  - **Complexity:** O(log n)
