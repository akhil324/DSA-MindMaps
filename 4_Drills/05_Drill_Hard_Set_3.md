# The Pattern Recognition Drill: Hard Set 3 (Questions 76-100)

**Goal:** This is the final challenge. These problems test the limits of your pattern recognition. Focus on breaking the problem down and identifying the core algorithmic idea, even if the implementation is complex.

---

**76. Merge k Sorted Lists**
> **Problem:** You are given an array of `k` linked-lists `lists`, each linked-list is sorted in ascending order. Merge all the linked-lists into one sorted linked-list and return its head.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/merge-k-sorted-lists/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Top K Elements**
  *   **Key Data Structure:** **Min-Heap**
  
  *   **The Clues (Why?):**
      *   The problem is an extension of "Merge Two Sorted Lists" to `k` lists.
      *   At each step of building the final merged list, you need to find the **smallest element** among the current heads of all `k` lists.
      *   This is a perfect use case for a **Min-Heap**. You can insert the heads of all `k` lists into the heap. To build the merged list, you repeatedly extract the minimum node from the heap, add it to your result, and then insert the next node from the same list back into the heap.

</details>

---

**77. N-Queens**
> **Problem:** The n-queens puzzle is the problem of placing `n` queens on an `n x n` chessboard such that no two queens attack each other. Given an integer `n`, return all distinct solutions to the n-queens puzzle.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/n-queens/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Backtracking**
  
  *   **The Clues (Why?):**
      *   The problem asks for **"all distinct solutions"**.
      *   This is a classic constraint satisfaction problem that requires exploring all possible placements.
      *   The backtracking logic is to try placing a queen in each column of a given row. If the placement is valid (doesn't conflict with previously placed queens), you recursively move to the next row. If you can't place a queen in a row, you **backtrack** and change the position of the queen in the previous row.

</details>

---

**78. Trapping Rain Water**
> **Problem:** Given `n` non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/trapping-rain-water/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers (or Dynamic Programming)**
  
  *   **The Clues (Why?):**
      *   The amount of water trapped above any bar is determined by `min(tallest_bar_to_the_left, tallest_bar_to_the_right) - current_bar_height`.
      *   **DP/Prefix-Postfix:** You can pre-compute the tallest bar to the left of every position in one pass and the tallest bar to the right in another pass. Then, a third pass can calculate the trapped water at each position.
      *   **Two Pointers:** A more space-efficient O(1) solution uses a `left` and `right` pointer at the ends of the array, along with `left_max` and `right_max` variables. You move the pointer corresponding to the smaller max height inward, calculating the trapped water as you go.

</details>

---

**79. Minimum Window Substring**
> **Problem:** Given two strings `s` and `t`, return the minimum window in `s` which will contain all the characters in `t`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/minimum-window-substring/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Sliding Window**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"minimum window"**, which is a **"substring"**. These are the strongest possible clues for the Sliding Window pattern.
      *   This is a classic dynamic-size window problem. You expand the window with a `right` pointer until it contains all the characters required by `t`. Then, you shrink the window from the `left` as much as possible while keeping it valid, updating your minimum window size at each step.

</details>

---

**80. Serialize and Deserialize Binary Tree**
> **Problem:** Design an algorithm to serialize a binary tree to a string and deserialize it back to the tree.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (BFS or DFS)**
  
  *   **The Clues (Why?):**
      *   To serialize, you must visit every node in a predictable order and record its value (and its structure, e.g., null children).
      *   **BFS (Level Order):** A common approach. You traverse level by level, adding node values or a null marker to a list, which is then joined into a string.
      *   **DFS (Pre-order):** Another excellent choice. A pre-order traversal is great because the root is always first, making reconstruction during deserialization very intuitive with a recursive helper function.

</details>

---

**81. Longest Consecutive Sequence**
> **Problem:** Given an unsorted array of integers `nums`, return the length of the longest consecutive elements sequence. You must write an algorithm that runs in O(n) time.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-consecutive-sequence/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **None (Uses a Data Structure cleverly)**
  *   **Key Data Structure:** **Hash Set**
  
  *   **The Clues (Why?):**
      *   The O(n) constraint rules out sorting (which would be O(n log n)).
      *   The problem is about finding sequences, but the numbers are not in order.
      *   A **Hash Set** allows for O(1) lookups. The clever trick is to first add all numbers to a set. Then, iterate through the numbers again. For each number, if it's the *start* of a sequence (i.e., `num - 1` is not in the set), then you start counting upwards (`num + 1`, `num + 2`, etc.) to find the length of the sequence starting at `num`.

</details>

---

**82. Word Search II**
> **Problem:** Given an `m x n` `board` of characters and a list of strings `words`, return all words on the board. Each word must be constructed from letters of sequentially adjacent cells, where adjacent cells are horizontally or vertically neighboring. The same letter cell may not be used more than once in a word.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/word-search-ii/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Backtracking + Trie**
  
  *   **The Clues (Why?):**
      *   Like Word Search I, this is a path-finding problem on a grid, which requires **Backtracking/DFS**.
      *   However, checking every word from the dictionary for every cell is too slow. The optimization is to use a **Trie**.
      *   You first build a Trie from all the words in the dictionary. Then, you perform a single DFS from each cell on the board. As you traverse, you also traverse the Trie. This allows you to find all words that start with the current path simultaneously and prune branches that don't correspond to any valid prefix.

</details>

---

**83. Find Median from Data Stream**
> **Problem:** Design a data structure that supports the following two operations: `void addNum(int num)` - Add an integer number from the data stream to the data structure. `double findMedian()` - Return the median of all elements so far.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/find-median-from-data-stream/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Heaps**
  
  *   **The Clues (Why?):**
      *   The problem requires you to efficiently find the median of a constantly growing list of numbers. Keeping the list sorted and finding the middle would be too slow (O(n) per insertion).
      *   The key insight is that the median is the element that separates the smaller half of the numbers from the larger half.
      *   You can maintain this separation using **two heaps**: a **Max-Heap** to store the smaller half of the numbers and a **Min-Heap** to store the larger half. The median can always be calculated in O(1) time from the roots of these two heaps.

</details>

---

**84. Regular Expression Matching**
> **Problem:** Given an input string `s` and a pattern `p`, implement regular expression matching with support for `.` and `*`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/regular-expression-matching/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   This is a classic matching problem where the solution depends on the solutions to subproblems.
      *   The state of the problem can be defined by `(i, j)`, representing whether the first `i` characters of `s` match the first `j` characters of `p`.
      *   The presence of the `*` character creates complex, overlapping subproblems (e.g., `*` can match zero, one, or more characters), making it a perfect candidate for a 2D DP table.

</details>

---

**85. Largest Rectangle in Histogram**
> **Problem:** Given an array of integers `heights` representing the histogram's bar height where the width of each bar is 1, return the area of the largest rectangle in the histogram.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/largest-rectangle-in-histogram/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Monotonic Stack**
  
  *   **The Clues (Why?):**
      *   The problem asks for the maximum area. The area of any rectangle is `height * width`.
      *   For any bar `h`, the largest rectangle it can be part of is limited by the first smaller bar to its left and the first smaller bar to its right.
      *   Finding the "next smaller element" and "previous smaller element" for every bar in the array is a classic use case for a **Monotonic Stack**, which allows you to solve this in O(n) time.

</details>

---

**86. Basic Calculator**
> **Problem:** Given a string `s` representing a valid expression, implement a basic calculator to evaluate it and return the result of the evaluation.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/basic-calculator/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Stack**
  
  *   **The Clues (Why?):**
      *   The problem involves evaluating an expression, especially one with parentheses.
      *   Parentheses create nested scopes of calculation. A **Stack** is the ideal data structure to handle this.
      *   When you encounter an opening parenthesis `(`, you can push the current result and sign onto the stack and start a new calculation. When you encounter a closing parenthesis `)`, you pop from the stack to restore the previous context.

</details>

---

**87. Minimum Knight Moves (Revisited)**
> **Problem:** In an infinite chessboard, a knight is at the `[0, 0]` square. Given the destination coordinates `[x, y]`, return the minimum number of moves to reach the destination.
>
> **Link:** [LeetCode Problem (Premium)](https://leetcode.com/problems/minimum-knight-moves/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Breadth-First Search (BFS)**
  
  *   **The Clues (Why?):**
      *   This is a classic **shortest path** problem on an unweighted, implicit graph (the chessboard).
      *   The keyword **"minimum number of moves"** is the strongest indicator for BFS.
      *   BFS explores the board layer by layer, guaranteeing that the first time you reach the target coordinates, it will be via the shortest possible path.

</details>

---

**88. Sliding Window Maximum**
> **Problem:** You are given an array of integers `nums`, there is a sliding window of size `k` which is moving from the very left of the array to the very right. You can only see the `k` numbers in the window. Each time the sliding window moves right by one position. Return the max sliding window.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/sliding-window-maximum/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Sliding Window + Deque**
  
  *   **The Clues (Why?):**
      *   The problem explicitly names the **"sliding window"** pattern.
      *   However, finding the maximum in the window at each step naively would be too slow.
      *   The optimal solution uses a **Deque (Double-Ended Queue)** to maintain a list of indices of elements in the current window, in decreasing order of their values. This makes finding the maximum (the front of the deque) an O(1) operation, leading to an overall O(n) solution.

</details>

---

**89. Edit Distance**
> **Problem:** Given two strings `word1` and `word2`, return the minimum number of operations required to convert `word1` to `word2`. You have the following three operations permitted on a word: Insert a character, Delete a character, Replace a character.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/edit-distance/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"minimum number of operations"** (an optimal value).
      *   This is a famous DP problem with optimal substructure. The edit distance between `word1` and `word2` depends on the edit distances of their prefixes.
      *   You can build a 2D DP table where `dp[i][j]` represents the minimum edit distance between the first `i` characters of `word1` and the first `j` characters of `word2`.

</details>

---

**90. The Skyline Problem**
> **Problem:** A city's skyline is the outer contour of the silhouette formed by all the buildings in that city when viewed from a distance. Given the locations and heights of all the buildings, return the skyline formed by these buildings collectively.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/the-skyline-problem/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Sweep-line Algorithm + Heap**
  
  *   **The Clues (Why?):**
      *   This is a geometric problem that can be solved by "sweeping" a vertical line across the x-axis.
      *   The key events are the start and end points of the buildings. You can represent each building as two points: a "start" point `(x, -height)` and an "end" point `(x, height)`.
      *   After sorting all these points, you process them in order. A **Max-Heap** is used to keep track of the heights of the buildings currently under the sweep line. A change in the maximum height in the heap signifies a new key point in the skyline.

</details>

---

**91. Longest Valid Parentheses**
> **Problem:** Given a string containing just the characters `'('` and `')'`, find the length of the longest valid (well-formed) parentheses substring.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-valid-parentheses/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Stack (or Dynamic Programming)**
  
  *   **The Clues (Why?):**
      *   The problem involves parentheses matching, which often suggests a **Stack**. The stack can be used to keep track of the indices of unmatched opening parentheses. When a closing parenthesis is found, you pop from the stack, and the length of the valid substring can be calculated from the current index and the new top of the stack.
      *   A **DP** solution is also possible, where `dp[i]` stores the length of the longest valid substring ending at index `i`.

</details>

---

**92. Best Time to Buy and Sell Stock III**
> **Problem:** You are given an array `prices`. You are permitted to complete **at most two transactions**. Find the maximum profit you can achieve.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   This is an optimization problem ("maximum profit") with a constraint ("at most two transactions").
      *   The state of the problem is more complex than the simpler versions. A DP state needs to track not just the day, but also how many transactions have been completed and whether you are currently holding a stock.
      *   A common DP state is `dp[k][i]`, representing the max profit on day `i` using at most `k` transactions.

</details>

---

**93. Sudoku Solver**
> **Problem:** Write a program to solve a Sudoku puzzle by filling the empty cells.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/sudoku-solver/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Backtracking**
  
  *   **The Clues (Why?):**
      *   This is the quintessential backtracking problem. You need to find a single valid solution by exploring possibilities.
      *   The algorithm is to find an empty cell, try placing a number from 1 to 9 in it, and check if the board is still valid. If it is, you recursively call the solver to fill the next empty cell. If the recursive call fails (hits a dead end), you **backtrack** by un-doing your choice (emptying the cell) and trying the next number.

</details>

---

**94. Binary Tree Maximum Path Sum**
> **Problem:** A path in a binary tree is a sequence of nodes where each pair of adjacent nodes in the sequence has an edge connecting them. A node can only appear in the sequence at most once. Return the maximum path sum of any non-empty path.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/binary-tree-maximum-path-sum/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem asks for a **"maximum path sum"** in a `Tree`.
      *   The path can start and end anywhere, which makes it complex.
      *   A post-order DFS traversal is the best approach. For each node, the recursive function needs to do two things:
          1.  **Calculate and return** the maximum path sum that *starts at the current node and goes downwards*. This is what the parent node needs to continue its path.
          2.  **Calculate and update** a global maximum for a path that might be "split" at the current node (i.e., `left_path + node.val + right_path`). This path cannot be extended upwards.

</details>

---

**95. Wildcard Matching**
> **Problem:** Given an input string `s` and a pattern `p`, implement wildcard pattern matching with support for `?` and `*`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/wildcard-matching/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   This is very similar to "Regular Expression Matching." It's a matching problem with special characters that create overlapping subproblems.
      *   The state `dp[i][j]` represents whether the first `i` characters of `s` match the first `j` characters of `p`. The logic for handling `*` (which can match any sequence of characters, including an empty sequence) makes DP the most robust approach.

</details>

---

**96. LRU Cache**
> **Problem:** Design a data structure that follows the constraints of a Least Recently Used (LRU) cache.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/lru-cache/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Combined Data Structures**
  *   **Key Data Structures:** **Hash Map + Doubly Linked List**
  
  *   **The Clues (Why?):**
      *   The problem requires two main operations to be fast: `get` (lookup) and `put` (insertion/update).
      *   A **Hash Map** is needed for O(1) lookup of keys.
      *   To manage the "least recently used" order, you need a data structure that allows for fast removal and addition of nodes at both ends. A **Doubly Linked List** is perfect for this. When a node is accessed, it's moved to the front (most recent). When the cache is full, the node at the back (least recent) is removed. The hash map stores keys and pointers to the nodes in the linked list.

</details>

---

**97. Text Justification**
> **Problem:** Given an array of strings `words` and a width `maxWidth`, format the text such that each line has exactly `maxWidth` characters and is fully (left and right) justified.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/text-justification/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy / Simulation**
  
  *   **The Clues (Why?):**
      *   This is a complex simulation and string manipulation problem.
      *   The core approach is **greedy**. At each step, you greedily pack as many words as you can fit onto a single line.
      *   Once you've determined which words go on a line, the rest of the problem is a careful implementation of the justification logic (calculating spaces, handling the last line differently, etc.).

</details>

---

**98. Median of Two Sorted Arrays**
> **Problem:** Given two sorted arrays `nums1` and `nums2` of size `m` and `n` respectively, return the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/median-of-two-sorted-arrays/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Modified Binary Search**
  
  *   **The Clues (Why?):**
      *   The O(log (m+n)) complexity requirement is a massive hint for a **binary search** approach.
      *   You cannot merge the arrays (that would be O(m+n)).
      *   The key insight is to binary search for the correct **partition** in the smaller array. The median is the value that partitions the combined dataset into two equal halves. By finding the right partition in `nums1`, the corresponding partition in `nums2` is automatically determined. The binary search helps you find this partition efficiently.

</details>

---

**99. Number of Atoms**
> **Problem:** Given a string `formula` representing a chemical formula, return the count of each atom.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/number-of-atoms/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Stack**
  
  *   **The Clues (Why?):**
      *   The problem involves parsing a formula with nested parentheses and multipliers.
      *   Parentheses create nested scopes, which is a classic use case for a **Stack**.
      *   You can use a stack of hash maps. When you see an opening parenthesis, you push a new hash map onto the stack. When you see a closing parenthesis, you pop the map, apply the multiplier, and merge its counts into the map now at the top of the stack.

</details>

---

**100. Critical Connections in a Network**
> **Problem:** You are given an integer `n` representing the number of servers and a list of `connections` representing the connections between them. A critical connection is a connection that, if removed, will make some servers unable to reach some other server. Return all critical connections in the network.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/critical-connections-in-a-network/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Graph Traversal (DFS) + Tarjan's Bridge-Finding Algorithm**
  
  *   **The Clues (Why?):**
      *   The problem is asking to find all **"bridges"** in an undirected `Graph`.
      *   This is a classic advanced graph problem that requires a modified **DFS**.
      *   Tarjan's algorithm uses a DFS traversal while keeping track of the "discovery time" and the "low-link value" for each node. A connection `u-v` is a bridge if the low-link value of `v` is greater than the discovery time of `u`.

</details>
