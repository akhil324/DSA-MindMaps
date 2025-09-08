# The Pattern Recognition Drill: Medium Set 1 (Questions 26-50)

**Goal:** These problems may require combining patterns or a deeper understanding of a pattern's variations. Identify the primary pattern and any key data structures.

---

**26. 3Sum**
> **Problem:** Given an integer array `nums`, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/3sum/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   The problem asks for **triplets** that sum to a target. This is a classic extension of the "pair with target sum" problem.
      *   The most efficient approach is to first **sort the array**. Then, you iterate through the array with a single pointer (`i`) and for each element, you run the **Two Pointers** pattern on the rest of the array (`left` and `right` pointers) to find a pair that sums to `-nums[i]`.

</details>

---

**27. Kth Largest Element in an Array**
> **Problem:** Given an integer array `nums` and an integer `k`, return the `k`th largest element in the array.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/kth-largest-element-in-an-array/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Top K Elements**
  *   **Key Data Structure:** **Min-Heap**
  
  *   **The Clues (Why?):**
      *   The problem explicitly asks for the **"kth largest"** element.
      *   While sorting (O(n log n)) works, a more optimal O(n log k) solution uses a Min-Heap of size `k`. You maintain a heap of the `k` largest elements seen so far. The root of this Min-Heap is the `k`th largest element at any given time.

</details>

---

**28. Longest Substring Without Repeating Characters**
> **Problem:** Given a string `s`, find the length of the longest substring without repeating characters.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Sliding Window (Dynamic Size)**
  *   **Key Data Structure:** **Hash Set or Hash Map**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"longest substring"**, a strong indicator for Sliding Window.
      *   The window's validity is defined by a condition ("without repeating characters"), which means its size must be dynamic.
      *   You use a Hash Set/Map to keep track of the characters currently in your window. If you encounter a character that's already in the set, you shrink the window from the left until the duplicate is removed.

</details>

---

**29. Combination Sum**
> **Problem:** Given an array of distinct integers `candidates` and a target integer `target`, return a list of all unique combinations of `candidates` where the chosen numbers sum to `target`. You may return the combinations in any order.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/combination-sum/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Subsets / Backtracking**
  
  *   **The Clues (Why?):**
      *   The problem asks for **"all unique combinations"**. The keyword "all" is a massive clue for backtracking.
      *   You need to explore all possible ways to form the target sum. The "choose, explore, unchoose" model fits perfectly. At each step, you can choose to include a number, then recursively explore the remaining target. If you go over, you backtrack (unchoose).

</details>

---

**30. Merge Intervals**
> **Problem:** Given an array of `intervals` where `intervals[i] = [starti, endi]`, merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/merge-intervals/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy (with Sorting)**
  
  *   **The Clues (Why?):**
      *   The problem involves finding an optimal set of non-overlapping intervals.
      *   The **greedy choice** is to first sort the intervals by their start time. This is a crucial first step.
      *   After sorting, you can iterate through the intervals and greedily merge the current interval with the previous one if they overlap. This local decision (merging adjacent overlapping intervals) leads to the global solution.

</details>

---

**31. Binary Tree Level Order Traversal**
> **Problem:** Given the `root` of a binary tree, return the level order traversal of its nodes' values. (i.e., from left to right, level by level).
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/binary-tree-level-order-traversal/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (BFS)**
  *   **Key Data Structure:** **Queue**
  
  *   **The Clues (Why?):**
      *   The problem explicitly asks for **"level order traversal"**.
      *   This is the definition of Breadth-First Search. A Queue is used to process nodes level by level, ensuring you visit all nodes at depth `d` before visiting any nodes at depth `d+1`.

</details>

---

**32. Number of Islands**
> **Problem:** Given an `m x n` 2D binary grid `grid` which represents a map of `'1'`s (land) and `'0'`s (water), return the number of islands.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/number-of-lands/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Graph Traversal (DFS or BFS)**
  
  *   **The Clues (Why?):**
      *   The problem can be modeled as a `Graph` where each land cell is a node and adjacent land cells have an edge between them.
      *   You need to find the number of **connected components** in this graph.
      *   The algorithm is to iterate through the grid. If you find a '1' (land), you increment your island count and then start a traversal (DFS or BFS) from that cell to find and "sink" all connected land cells (e.g., by changing them to '0') so you don't count them again.

</details>

---

**33. Product of Array Except Self**
> **Problem:** Given an integer array `nums`, return an array `answer` such that `answer[i]` is equal to the product of all the elements of `nums` except `nums[i]`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/product-of-array-except-self/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Prefix/Postfix Calculation**
  
  *   **The Clues (Why?):**
      *   The problem has a constraint that you cannot use the division operation and must solve it in O(n) time.
      *   The key insight is that the product except self at index `i` is `(product of all elements to the left of i) * (product of all elements to the right of i)`.
      *   You can calculate all the prefix products in one pass and all the postfix products in a second pass, then combine them.

</details>

---

**34. Permutations**
> **Problem:** Given an array `nums` of distinct integers, return all the possible permutations. You can return the answer in any order.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/permutations/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Subsets / Backtracking**
  
  *   **The Clues (Why?):**
      *   The problem asks for **"all possible permutations"**. The keyword "all" is a strong signal for backtracking.
      *   You need to explore every possible ordering of the elements. The recursive "choose, explore, unchoose" approach works perfectly. You choose an available number, recursively generate permutations for the rest, and then backtrack to try a different number in the current position.

</details>

---

**35. Search in Rotated Sorted Array**
> **Problem:** There is an integer array `nums` sorted in ascending order (with distinct values), which is possibly rotated. Given the array `nums` and an integer `target`, return the index of `target` if it is in `nums`, or `-1` if it is not in `nums`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/search-in-rotated-sorted-array/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Modified Binary Search**
  
  *   **The Clues (Why?):**
      *   The problem explicitly states it's a **"sorted array"** that has been **"rotated"**.
      *   You are required to solve it in O(log n) time, which immediately rules out a linear scan and points directly to a binary search variant.
      *   The core logic involves first identifying which half of the current search space is still sorted, then checking if the target lies within that sorted portion to decide where to search next.

</details>

---

**36. Container With Most Water**
> **Problem:** You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `i`th line are `(i, 0)` and `(i, height[i])`. Find two lines that together with the x-axis form a container, such that the container contains the most water.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/container-with-most-water/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   The problem asks for an optimal **pair** of lines.
      *   The brute-force O(n²) solution (checking every pair) is too slow.
      *   An O(n) solution uses two pointers, one at the `left` end and one at the `right`. You calculate the area. The key insight (the greedy choice) is to move the pointer corresponding to the *shorter* line inward, because moving the taller line's pointer can never increase the area.

</details>

---

**37. K Closest Points to Origin**
> **Problem:** Given an array of `points` where `points[i] = [xi, yi]` represents a point on the X-Y plane and an integer `k`, return the `k` closest points to the origin `(0, 0)`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/k-closest-points-to-origin/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Top K Elements**
  *   **Key Data Structure:** **Max-Heap**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"`k` closest"** points.
      *   This is a variation of the Top K pattern. You need to find the `k` elements with the *smallest* distance.
      *   The optimal approach uses a **Max-Heap** of size `k`. You iterate through the points, and if a point's distance is smaller than the largest distance currently in the heap (the root), you pop the root and push the new point.

</details>

---

**38. Coin Change**
> **Problem:** You are given an integer array `coins` representing coins of different denominations and an integer `amount`. Return the fewest number of coins that you need to make up that amount.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/coin-change/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"fewest number"** (an optimal value).
      *   It has optimal substructure: the fewest coins to make `amount` depends on the fewest coins to make smaller amounts (e.g., `amount - coin`).
      *   A greedy approach (always taking the largest coin) doesn't work for all coin sets. Therefore, you must explore all possibilities, making it a classic DP problem.

</details>

---

**39. Validate Binary Search Tree**
> **Problem:** Given the `root` of a binary tree, determine if it is a valid binary search tree (BST).
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/validate-binary-search-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem requires you to validate a property of a `Tree` across all its nodes.
      *   The definition of a BST is recursive. A simple check `root.left.val < root.val < root.right.val` is not enough. The *entire* left subtree must be less than the root, and the *entire* right subtree must be greater.
      *   The best approach is a recursive DFS where you pass down `min` and `max` bounds to check the validity of each subtree.

</details>

---

**40. Course Schedule**
> **Problem:** There are a total of `numCourses` courses you have to take, labeled from `0` to `numCourses - 1`. You are given an array `prerequisites` where `prerequisites[i] = [ai, bi]` indicates that you must take course `bi` first if you want to take course `ai`. Return `true` if you can finish all courses. Otherwise, return `false`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/course-schedule/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Topological Sort**
  
  *   **The Clues (Why?):**
      *   The problem is explicitly about **dependencies** and **prerequisites**.
      *   This can be modeled as a `Directed Graph` where an edge `bi -> ai` means `bi` is a prerequisite for `ai`.
      *   The question "can you finish all courses?" is equivalent to asking "does this graph have a cycle?". If there is a cycle (e.g., A requires B, and B requires A), it's impossible. A topological sort algorithm will detect this cycle.

</details>

---

**41. Jump Game**
> **Problem:** You are given an integer array `nums`. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position. Return `true` if you can reach the last index, or `false` otherwise.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/jump-game/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy**
  
  *   **The Clues (Why?):**
      *   This is an optimization problem disguised as a path-finding problem. You need to find if *any* path exists.
      *   The **greedy choice** is to always make the jump that gets you the farthest.
      *   You can solve this in O(n) time by iterating through the array and keeping track of the `max_reach` possible from all the positions you've visited so far. If your current position `i` ever becomes greater than `max_reach`, you know you're stuck.

</details>

---

**42. Clone Graph**
> **Problem:** Given a reference of a node in a connected undirected graph. Return a deep copy (clone) of the graph.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/clone-graph/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Graph Traversal (DFS or BFS)**
  *   **Key Data Structure:** **Hash Map**
  
  *   **The Clues (Why?):**
      *   The problem requires you to visit every node and every edge of a `Graph` to replicate it.
      *   A traversal (either DFS or BFS) is necessary to explore the entire graph.
      *   A **Hash Map** is crucial to store the mapping between the original nodes and their newly created clones. This prevents you from re-cloning a node you've already visited and helps you connect the edges correctly.

</details>

---

**43. Top K Frequent Elements**
> **Problem:** Given an integer array `nums` and an integer `k`, return the `k` most frequent elements.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/top-k-frequent-elements/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Top K Elements**
  *   **Key Data Structure:** **Hash Map + Min-Heap**
  
  *   **The Clues (Why?):**
      *   The problem explicitly asks for the **"`k` most frequent"** elements.
      *   This is a two-step problem. First, you need to count the frequency of each number, which is a perfect job for a **Hash Map**.
      *   Second, from the frequency map, you need to find the `k` entries with the highest frequencies. This is a classic **Top K Elements** problem, best solved with a Min-Heap of size `k`.

</details>

---

**44. Find Minimum in Rotated Sorted Array**
> **Problem:** Suppose an array of length `n` sorted in ascending order is rotated. For example, the array `[0,1,2,4,5,6,7]` might become `[4,5,6,7,0,1,2]`. Given the array `nums`, return the minimum element of this array.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Modified Binary Search**
  
  *   **The Clues (Why?):**
      *   The problem involves a **"rotated sorted array"** and asks for the minimum element.
      *   The O(log n) time complexity requirement points directly to binary search.
      *   The minimum element is the "pivot" or "inflection point". You can find it by using binary search to determine which half of the search space contains the inflection point.

</details>

---

**45. Word Break**
> **Problem:** Given a string `s` and a dictionary of strings `wordDict`, return `true` if `s` can be segmented into a space-separated sequence of one or more dictionary words.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/word-break/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks if a solution is **possible**.
      *   It has optimal substructure. A string `s` can be broken down if `s.substring(0, i)` is a valid word in the dictionary AND the rest of the string `s.substring(i)` can also be broken down.
      *   This leads to overlapping subproblems (you might check if `s.substring(i)` can be broken down multiple times). A 1D DP array `dp[i]` can store whether the string up to index `i` is breakable.

</details>

---

**46. House Robber**
> **Problem:** You are a professional robber planning to rob houses along a street. Each house has a certain amount of money. The only constraint stopping you is that adjacent houses have security systems connected, and it will automatically contact the police if two adjacent houses were broken into on the same night. Given an integer array `nums` representing the amount of money of each house, return the maximum amount of money you can rob tonight without alerting the police.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/house-robber/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"maximum amount"** (an optimal value).
      *   It has optimal substructure. The maximum money you can rob up to house `i` is the maximum of two choices: 1) Rob house `i` (and add its value to the max you could rob up to house `i-2`), or 2) Don't rob house `i` (in which case the max is whatever you could rob up to house `i-1`).

</details>

---

**47. Longest Increasing Subsequence**
> **Problem:** Given an integer array `nums`, return the length of the longest strictly increasing subsequence.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/longest-increasing-subsequence/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"longest"** subsequence (an optimal value).
      *   Note the difference: a **subsequence** is not necessarily contiguous, unlike a **subarray**. This makes Sliding Window inapplicable.
      *   This is a classic DP problem. You can use a DP array where `dp[i]` stores the length of the longest increasing subsequence that *ends* with the element `nums[i]`.

</details>

---

**48. Palindrome Partitioning**
> **Problem:** Given a string `s`, partition `s` such that every substring of the partition is a palindrome. Return all possible palindrome partitioning of `s`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/palindrome-partitioning/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Subsets / Backtracking**
  
  *   **The Clues (Why?):**
      *   The problem asks for **"all possible"** partitions. This is a very strong indicator for backtracking.
      *   You need to explore every way to split the string. The recursive logic is: try making a cut at every possible position `i`. If the substring from your last cut to `i` is a palindrome, then "choose" it and recursively explore the rest of the string from `i+1`. Then "unchoose" and try the next possible cut.

</details>

---

**49. Gas Station**
> **Problem:** There are `n` gas stations along a circular route, where the amount of gas at the `i`th station is `gas[i]`. You have a car with an unlimited gas tank and it costs `cost[i]` of gas to travel from the `i`th station to its next station. You begin the journey with an empty tank at one of the gas stations. Given two integer arrays `gas` and `cost`, return the starting gas station's index if you can travel around the circuit once in the clockwise direction, otherwise return -1.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/gas-station/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy**
  
  *   **The Clues (Why?):**
      *   The problem asks for a valid starting point. While you could brute-force check every starting point, there's a more clever approach.
      *   The key **greedy insight** is that if the total amount of `gas` is less than the total `cost`, no solution is possible. If a solution *is* possible, and you start at station `A` and run out of gas before reaching station `B`, then no station between `A` and `B` can be a valid starting point either. This allows you to eliminate sections of the route and find the solution in a single pass.

</details>

---

**50. Lowest Common Ancestor of a Binary Search Tree**
> **Problem:** Given a binary search tree (BST), find the lowest common ancestor (LCA) of two given nodes in the BST.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (using BST properties)**
  
  *   **The Clues (Why?):**
      *   The problem involves a `Tree`, but crucially, it's a **Binary Search Tree (BST)**. This property is key.
      *   You don't need a full traversal. You can start at the root and use the BST property to decide where the two nodes `p` and `q` lie relative to the current node.
      *   If both `p` and `q` are smaller than the current node, the LCA must be in the left subtree. If both are larger, it must be in the right. If they split (one is smaller, one is larger), then the current node *is* the LCA.

</details>
