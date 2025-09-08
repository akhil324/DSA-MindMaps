# The Pattern Recognition Drill: Medium/Hard Set 2 (Questions 51-75)

**Goal:** This set increases in complexity. Focus on identifying the core pattern, even if the implementation seems tricky. Many problems combine multiple ideas.

---

**51. Word Search**
> **Problem:** Given an `m x n` grid of characters `board` and a string `word`, return `true` if `word` exists in the grid. The word can be constructed from letters of sequentially adjacent cells, where adjacent cells are horizontally or vertically neighboring. The same letter cell may not be used more than once.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/word-search/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Backtracking (on a Grid/Graph)**
  
  *   **The Clues (Why?):**
      *   The problem asks you to **find a path** that spells out a word.
      *   You need to explore multiple possible paths from each cell. If a path leads to a dead end (the next character doesn't match), you must **backtrack** and try a different direction (up, down, left, or right).
      *   This is a classic application of recursive DFS with backtracking on a 2D grid.

</details>

---

**52. Find All Anagrams in a String**
> **Problem:** Given two strings `s` and `p`, return an array of all the start indices of `p`'s anagrams in `s`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/find-all-anagrams-in-a-string/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Sliding Window**
  *   **Key Data Structure:** **Hash Map (or Array as Frequency Counter)**
  
  *   **The Clues (Why?):**
      *   The problem asks you to find occurrences of a permutation of `p` within `s`. An anagram will always be a **contiguous substring** of the same length as `p`.
      *   This is a perfect fit for a **fixed-size sliding window** where the window size is `len(p)`.
      *   You use a hash map to store the character frequencies of `p`. As your window slides over `s`, you maintain a frequency map of the characters inside the window and compare it to `p`'s map.

</details>

---

**53. Course Schedule II**
> **Problem:** This is a follow-up to Course Schedule. This time, return the ordering of courses you should take to finish all courses. If there are many valid answers, return any of them. If it is impossible to finish all courses, return an empty array.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/course-schedule-ii/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Topological Sort**
  
  *   **The Clues (Why?):**
      *   Like its predecessor, this problem is about **dependencies** and **prerequisites**, which defines a Directed Acyclic Graph (DAG).
      *   Instead of just detecting a cycle, it explicitly asks for a **valid ordering**, which is the direct output of a topological sort algorithm (like Kahn's algorithm).

</details>

---

**54. Longest Palindromic Substring**
> **Problem:** Given a string `s`, return the longest palindromic substring in `s`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-palindromic-substring/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers (or Dynamic Programming)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"longest substring"** that is a **"palindrome"**.
      *   **Two Pointers ("Expand from Center"):** This is a very clever O(n²) approach. You iterate through each character of the string and treat it as a potential center of a palindrome. From each center, you use two pointers to expand outwards as long as the characters match. You must handle both odd-length (center is one char) and even-length (center is between two chars) palindromes.
      *   **Dynamic Programming:** A more formal O(n²) approach where `dp[i][j]` is true if the substring from `i` to `j` is a palindrome.

</details>

---

**55. 01 Matrix**
> **Problem:** Given an `m x n` binary matrix `mat`, return the distance of the nearest `0` for each cell. The distance between two adjacent cells is 1.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/01-matrix/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Breadth-First Search (BFS)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"nearest"** distance, which is synonymous with the **"shortest path"**.
      *   Shortest path problems on an unweighted grid/graph are a classic use case for BFS.
      *   The trick is to start a multi-source BFS. You add all cells that are `0` to the queue initially (with distance 0) and then explore outwards, level by level, filling in the distances for the `1`s.

</details>

---

**56. Kth Smallest Element in a BST**
> **Problem:** Given the `root` of a binary search tree, and an integer `k`, return the `k`th smallest value (1-indexed) of all the values of the nodes in the tree.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS - Inorder)**
  
  *   **The Clues (Why?):**
      *   The problem involves a **Binary Search Tree (BST)**.
      *   The key property of a BST is that an **inorder traversal** (Left -> Root -> Right) visits the nodes in ascending sorted order.
      *   Therefore, you can perform an inorder traversal and simply stop at the `k`th element you visit.

</details>

---

**57. Group Anagrams**
> **Problem:** Given an array of strings `strs`, group the anagrams together. You can return the answer in any order.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/group-anagrams/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **None (Uses a Data Structure directly)**
  *   **Key Data Structure:** **Hash Map**
  
  *   **The Clues (Why?):**
      *   The problem requires you to **group** items based on a shared property (being an anagram).
      *   A Hash Map is perfect for grouping. The challenge is finding the right **key**. A canonical representation of each word (like the sorted version of the string, e.g., "eat", "tea", "ate" all become "aet") can serve as the key. The value in the map would be a list of all strings that map to that key.

</details>

---

**58. Subsets II**
> **Problem:** Given an integer array `nums` that may contain duplicates, return all possible subsets (the power set). The solution set must not contain duplicate subsets.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/subsets-ii/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Subsets / Backtracking**
  
  *   **The Clues (Why?):**
      *   The problem asks for **"all possible subsets"**, a clear sign for backtracking.
      *   The twist is handling **duplicates**. The standard backtracking template needs a modification. After sorting the input array, you add a check inside your loop to skip an element if it's the same as the previous one and you are not picking it for the first time at this level of recursion.

</details>

---

**59. Daily Temperatures**
> **Problem:** Given an array of integers `temperatures` represents the daily temperatures, return an array `answer` such that `answer[i]` is the number of days you have to wait after the `i`th day to get a warmer temperature. If there is no future day for which this is possible, keep `answer[i] == 0` instead.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/daily-temperatures/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Monotonic Stack**
  *   **Key Data Structure:** **Stack**
  
  *   **The Clues (Why?):**
      *   The problem asks to find the **"next greater element"** for each item in the array.
      *   This is the classic use case for a Monotonic Stack. You iterate through the temperatures and maintain a stack of indices of days with decreasing temperatures. When you encounter a temperature that is warmer than the temperature at the top of the stack, you've found the "next greater element" for the index on the stack, so you can pop it and calculate the day difference.

</details>

---

**60. Partition Labels**
> **Problem:** You are given a string `s`. We want to partition the string into as many parts as possible so that each letter appears in at most one part. Return a list of integers representing the size of these parts.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/partition-labels/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy**
  
  *   **The Clues (Why?):**
      *   The problem asks to partition into **"as many parts as possible"**, which is an optimization goal.
      *   The **greedy choice** involves finding the smallest possible valid partition at each step.
      *   The algorithm is to first find the last occurrence of every character. Then, iterate through the string, keeping track of the `max_last_pos` for all characters seen in the current partition. A partition can be closed at index `i` only if `i == max_last_pos`.

</details>

---

**61. Time Based Key-Value Store**
> **Problem:** Design a time-based key-value data structure that can store multiple values for the same key at different time stamps and retrieve the key's value at a certain timestamp.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/time-based-key-value-store/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Modified Binary Search**
  *   **Key Data Structure:** **Hash Map**
  
  *   **The Clues (Why?):**
      *   The `get` operation asks for a value at a `timestamp_prev` that is less than or equal to the given `timestamp`.
      *   The data for each key can be stored in a list of `(timestamp, value)` pairs, which will be naturally sorted by timestamp.
      *   This turns the `get` operation into a search on a **sorted list**, making **Binary Search** the optimal pattern to find the correct timestamp.

</details>

---

**62. Accounts Merge**
> **Problem:** Given a list of `accounts` where each element `accounts[i]` is a list of strings, where the first element is a name, and the rest of the elements are emails. Now, we would like to merge these accounts. Two accounts definitely belong to the same person if there is some common email to both accounts.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/accounts-merge/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Graph Traversal (DFS) or Union-Find**
  
  *   **The Clues (Why?):**
      *   The problem is about finding **connected components**. You can model this as a `Graph` where each email is a node. An edge exists between two emails if they appear in the same account.
      *   **Graph Traversal:** You can build this graph and then use DFS or BFS to find the connected components (groups of merged emails).
      *   **Union-Find:** This is a more advanced but highly efficient data structure specifically designed for this type of "grouping" or "connectivity" problem.

</details>

---

**63. Encode and Decode Strings**
> **Problem:** Design an algorithm to encode a list of strings to a single string. The encoded string is then sent over the network and is decoded back to the original list of strings.
>
> **Link:** [LeetCode Problem (Premium)](https://leetcode.com/problems/encode-and-decode-strings/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **String Manipulation / Protocol Design**
  
  *   **The Clues (Why?):**
      *   This is a design problem, not a standard algorithmic pattern. The challenge is handling edge cases, like empty strings or strings containing special characters.
      *   A common solution is to create a simple protocol, like `length#string`. For example, `["hello", "world"]` becomes `"5#hello5#world"`. The decoder reads the length, then the delimiter `#`, then reads that many characters to reconstruct the string, and repeats.

</details>

---

**64. Longest Repeating Character Replacement**
> **Problem:** You are given a string `s` and an integer `k`. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most `k` times. Return the length of the longest substring containing the same letter you can get after performing the above operations.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-repeating-character-replacement/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Sliding Window**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"longest substring"**.
      *   The window's validity is determined by a condition: `window_length - count_of_most_frequent_char <= k`.
      *   This is a dynamic sliding window where you expand the window to the right, and if the condition is violated, you shrink it from the left.

</details>

---

**65. Spiral Matrix**
> **Problem:** Given an `m x n` `matrix`, return all elements of the `matrix` in spiral order.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/spiral-matrix/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Matrix Traversal / Simulation**
  
  *   **The Clues (Why?):**
      *   This is a simulation problem. There isn't a high-level DSA pattern; you need to implement the traversal logic directly.
      *   The common approach is to maintain four boundary pointers: `top`, `bottom`, `left`, and `right`. You traverse the top row, then the right column, then the bottom row, then the left column, shrinking the boundaries inward after each pass until they cross.

</details>

---

**66. Minimum Knight Moves**
> **Problem:** In an infinite chessboard, a knight is at the `[0, 0]` square. Given the destination coordinates `[x, y]`, return the minimum number of moves to reach the destination.
>
> **Link:** [LeetCode Problem (Premium)](https://leetcode.com/problems/minimum-knight-moves/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Breadth-First Search (BFS)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"minimum number of moves"**.
      *   This is a classic **shortest path** problem on an unweighted graph (the chessboard).
      *   BFS is the guaranteed algorithm for finding the shortest path in an unweighted graph. You start at `(0,0)` and explore all possible knight moves level by level until you reach the target coordinates.

</details>

---

**67. Rotting Oranges**
> **Problem:** You are given an `m x n` `grid` where each cell can have one of three values: `0` representing an empty cell, `1` representing a fresh orange, or `2` representing a rotten orange. Every minute, any fresh orange that is 4-directionally adjacent to a rotten orange becomes rotten. Return the minimum number of minutes that must elapse until no cell has a fresh orange.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/rotting-oranges/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Breadth-First Search (BFS)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"minimum number of minutes"**.
      *   The process of rotting spreads outwards **level by level** each minute. This is a perfect analogy for a BFS traversal.
      *   This is a multi-source BFS problem. You start by adding all initially rotten oranges to the queue. Each "level" of the BFS corresponds to one minute passing.

</details>

---

**68. Reorder List**
> **Problem:** You are given the head of a singly linked list. The list can be represented as: `L0 → L1 → … → Ln - 1 → Ln`. Reorder the list to be on the following form: `L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → …`
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/reorder-list/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Fast & Slow Pointers**
  
  *   **The Clues (Why?):**
      *   This is a complex `Linked List` manipulation problem.
      *   The solution is a multi-step process that relies on core linked list patterns:
          1.  Find the middle of the list using **Fast & Slow Pointers**.
          2.  Split the list into two halves.
          3.  Reverse the second half.
          4.  Merge the two halves together in the required order.

</details>

---

**69. Pacific Atlantic Water Flow**
> **Problem:** You are given an `m x n` integer `matrix` `heights` representing the height of each unit cell in a continent. The Pacific ocean touches the continent's left and top edges, and the Atlantic ocean touches the right and bottom edges. Water can flow from any cell to an adjacent cell with an equal or lower height. Return a 2D list of grid coordinates `result` where `result[i] = [ri, ci]` denotes that rain water can flow from cell `(ri, ci)` to both the Pacific and Atlantic oceans.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/pacific-atlantic-water-flow/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Graph Traversal (DFS or BFS)**
  
  *   **The Clues (Why?):**
      *   The problem is about reachability on a grid, which is a `Graph` problem.
      *   The key insight is to work backward. Instead of checking where water can flow *from* each cell, find all the cells that can flow *to* the Pacific and all the cells that can flow *to* the Atlantic.
      *   You can start two separate traversals (DFS or BFS), one from all the Pacific border cells and one from all the Atlantic border cells. The answer is the set of cells that are reachable in both traversals.

</details>

---

**70. Word Ladder**
> **Problem:** A transformation sequence from word `beginWord` to `endWord` using a dictionary `wordList` is a sequence of words `beginWord -> s1 -> s2 -> ... -> sk` such that every adjacent pair of words differs by a single letter. Given two words, `beginWord` and `endWord`, and a dictionary `wordList`, return the length of the shortest transformation sequence from `beginWord` to `endWord`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/word-ladder/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Breadth-First Search (BFS)**
  
  *   **The Clues (Why?):**
      *   The problem explicitly asks for the **"shortest"** transformation sequence.
      *   This can be modeled as a shortest path problem on an unweighted `Graph`. Each word in the `wordList` is a node, and an edge exists between two words if they differ by only one letter.
      *   BFS is the perfect algorithm to find the shortest path from `beginWord` to `endWord` in this implicit graph.

</details>

---

**71. Longest Common Subsequence**
> **Problem:** Given two strings `text1` and `text2`, return the length of their longest common subsequence.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-common-subsequence/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"longest"** common subsequence (an optimal value).
      *   A **subsequence** is not necessarily contiguous, ruling out Sliding Window.
      *   This is one of the most classic DP problems. It has optimal substructure: the LCS of `text1` and `text2` depends on the LCS of their prefixes. You can build a 2D DP table where `dp[i][j]` stores the length of the LCS of `text1[0...i-1]` and `text2[0...j-1]`.

</details>

---

**72. Alien Dictionary**
> **Problem:** There is a new alien language that uses the English alphabet. However, the order among the letters is unknown to you. You are given a list of strings `words` from the alien language's dictionary, where the strings in `words` are sorted lexicographically by the rules of this new language. Return a string of the unique letters in the new alien language sorted in lexicographically increasing order.
>
> **Link:** [LeetCode Problem (Premium)](https://leetcode.com/problems/alien-dictionary/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Topological Sort**
  
  *   **The Clues (Why?):**
      *   The problem is about finding a valid **ordering** of characters based on **dependencies**.
      *   You can infer dependencies by comparing adjacent words. For example, if "wrt" comes before "wrf", you know that 't' must come before 'f'. This `t -> f` is a directed edge in a graph of characters.
      *   By building a graph of all such dependencies, the problem becomes finding a valid linear ordering of the nodes, which is exactly what a topological sort does.

</details>

---

**73. Meeting Rooms II**
> **Problem:** Given an array of meeting time `intervals` consisting of start and end times, find the minimum number of conference rooms required.
>
> **Link:** [LeetCode Problem (Premium)](https://leetcode.com/problems/meeting-rooms-ii/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy (with Sorting and a Min-Heap)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"minimum number"** of rooms, an optimization problem.
      *   The **greedy choice** is to sort the meetings by their start times.
      *   As you iterate through the sorted meetings, you need to efficiently track when rooms become free. A **Min-Heap** is the perfect data structure for this. It can store the end times of all meetings currently in progress. The size of the heap at any point represents the number of rooms needed, and the root always tells you which room will free up next.

</details>

---

**74. Palindromic Substrings**
> **Problem:** Given a string `s`, return the number of palindromic substrings in it.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/palindromic-substrings/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers (Expand from Center)**
  
  *   **The Clues (Why?):**
      *   The problem asks you to **count all** palindromic substrings.
      *   Similar to "Longest Palindromic Substring," the most intuitive and efficient approach is to iterate through the string and treat each position as a potential center of a palindrome.
      *   From each center (both odd and even length), you use two pointers to expand outwards, incrementing your count for every valid palindrome you find.

</details>

---

**75. Insert Interval**
> **Problem:** You are given an array of non-overlapping intervals `intervals` where `intervals[i] = [starti, endi]` represent the start and the end of the `i`th interval and `intervals` is sorted in ascending order by `starti`. You are also given an interval `newInterval = [start, end]` that represents the start and end of another interval. Insert `newInterval` into `intervals` such that `intervals` is still sorted and non-overlapping.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/insert-interval/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy / Interval Manipulation**
  
  *   **The Clues (Why?):**
      *   The input array is **sorted**, which is a significant clue.
      *   This is an interval manipulation problem. The logic can be broken down into three greedy phases:
          1.  Add all intervals that come *before* `newInterval` (their end is less than `newInterval`'s start).
          2.  Merge `newInterval` with all intervals it overlaps with.
          3.  Add all remaining intervals that come *after* the merged interval.

</details>
