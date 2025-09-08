# The Pattern Recognition Drill: Easy Set 1 (Questions 1-25)

**Goal:** For each problem, your task is not to solve it, but to **identify the primary pattern** and the **key data structure** needed. Use the Diagnostic Toolkit to help you. Click the dropdown to verify your diagnosis and understand the "why."

---

**1. Two Sum**
> **Problem:** Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/two-sum/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **None (Uses a Data Structure directly)**
  *   **Key Data Structure:** **Hash Map**
  
  *   **The Clues (Why?):**
      *   The problem asks you to find a **pair** of numbers.
      *   The array is **not sorted**, so Two Pointers won't work efficiently.
      *   You need a way to check for the existence of `target - current_number` very quickly. A Hash Map provides an O(1) lookup, making it the perfect tool to store numbers you've already seen.

</details>

---

**2. Reverse String**
> **Problem:** Write a function that reverses a string. The input string is given as an array of characters `s`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/reverse-string/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   The problem involves modifying an array in-place from opposite ends.
      *   The core logic involves swapping the first character with the last, the second with the second-to-last, and so on, until the pointers meet in the middle. This is a classic "converging pointers" scenario.

</details>

---

**3. Valid Parentheses**
> **Problem:** Given a string `s` containing just the characters `(`, `)`, `{`, `}`, `[` and `]`, determine if the input string is valid.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/valid-parentheses/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **None (Uses a Data Structure directly)**
  *   **Key Data Structure:** **Stack**
  
  *   **The Clues (Why?):**
      *   The problem has a "Last-In, First-Out" (LIFO) logic. When you see a closing bracket, it must match the *most recently seen* opening bracket.
      *   A Stack is the perfect data structure for LIFO operations. You push opening brackets onto the stack and pop them when you find a matching closing bracket.

</details>

---

**4. Merge Two Sorted Lists**
> **Problem:** You are given the heads of two sorted linked lists. Merge the two lists into one sorted list.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/merge-two-sorted-lists/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   You are dealing with two **sorted** data structures (`Linked Lists`).
      *   You need to compare elements from both lists simultaneously to build a new sorted list. You'll use one pointer for each list to keep track of your current position as you build the merged list.

</details>

---

**5. Maximum Depth of Binary Tree**
> **Problem:** Given the `root` of a binary tree, return its maximum depth.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem involves a `Tree` and asks for a property related to its height/depth.
      *   You need to explore paths from the root to the leaves.
      *   A recursive DFS approach is the most intuitive way to solve this: the max depth of a tree is `1 + max(depth of left subtree, depth of right subtree)`. This naturally leads to a recursive solution.

</details>

---

**6. Contains Duplicate**
> **Problem:** Given an integer array `nums`, return `true` if any value appears at least twice in the array, and `false` if every element is distinct.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/contains-duplicate/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **None (Uses a Data Structure directly)**
  *   **Key Data Structure:** **Hash Set**
  
  *   **The Clues (Why?):**
      *   You need to keep track of the numbers you have already seen.
      *   A Hash Set provides O(1) average time complexity for both adding an element and checking if an element already exists. This is far more efficient than a brute-force O(n²) check.

</details>

---

**7. Valid Palindrome**
> **Problem:** A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Given a string `s`, return `true` if it is a palindrome, or `false` otherwise.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/valid-palindrome/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   The core of the problem is comparing characters from the beginning and the end of the string simultaneously.
      *   This is a classic use case for two pointers, one starting at the left and one at the right, moving towards the center.

</details>

---

**8. Linked List Cycle**
> **Problem:** Given `head`, the head of a linked list, determine if the linked list has a cycle in it.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/linked-list-cycle/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Fast & Slow Pointers**
  
  *   **The Clues (Why?):**
      *   The problem involves a `Linked List` and asks about its structural properties (specifically, a `cycle`).
      *   This is the quintessential problem for the Fast & Slow Pointers pattern. The "hare and tortoise" will only meet if they are running on a circular track.

</details>

---

**9. Binary Tree Inorder Traversal**
> **Problem:** Given the `root` of a binary tree, return the inorder traversal of its nodes' values.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/binary-tree-inorder-traversal/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem explicitly asks you to **traverse** a `Tree`.
      *   Inorder traversal (Left -> Root -> Right) is a specific type of Depth-First Search. A recursive solution is the most direct way to implement this.

</details>

---

**10. Best Time to Buy and Sell Stock**
> **Problem:** You are given an array `prices` where `prices[i]` is the price of a given stock on the `i`th day. You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers (or a single-pass approach that mimics it)**
  
  *   **The Clues (Why?):**
      *   You need to find the maximum difference between two elements (`sell_price - buy_price`).
      *   A simple and efficient O(n) approach is to iterate through the array, keeping track of the minimum price found *so far* (the best day to buy). At each step, you calculate the potential profit if you sold today. This can be framed as a two-pointer problem where one pointer tracks the minimum and the other iterates.

</details>

---

**11. Climbing Stairs**
> **Problem:** You are climbing a staircase. It takes `n` steps to reach the top. Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/climbing-stairs/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"number of ways"** to do something.
      *   It has **optimal substructure** and **overlapping subproblems**. The number of ways to get to step `n` is the sum of the ways to get to step `n-1` and the ways to get to step `n-2`. This is the Fibonacci sequence, a classic DP problem.

</details>

---

**12. Middle of the Linked List**
> **Problem:** Given the `head` of a singly linked list, return the middle node of the linked list.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/middle-of-the-linked-list/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Fast & Slow Pointers**
  
  *   **The Clues (Why?):**
      *   The problem involves a `Linked List` and asks to find a specific node (the `middle`).
      *   This is a textbook application of this pattern. When the fast pointer (moving two steps at a time) reaches the end, the slow pointer (moving one step at a time) will be at the middle.

</details>

---

**13. Invert Binary Tree**
> **Problem:** Given the `root` of a binary tree, invert the tree, and return its root.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/invert-binary-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS or BFS)**
  
  *   **The Clues (Why?):**
      *   The problem requires you to visit every node in a `Tree` and perform an operation (swapping its left and right children).
      *   This can be done with either DFS (a recursive approach is very clean) or BFS (an iterative, level-by-level approach). Both are valid traversal strategies.

</details>

---

**14. Maximum Subarray**
> **Problem:** Given an integer array `nums`, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/maximum-subarray/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Dynamic Programming (Kadane's Algorithm)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **maximum sum** of a **contiguous subarray**.
      *   While it has "contiguous subarray" (a Sliding Window clue), the window size is not fixed and can be negative, making standard sliding window tricky.
      *   The problem has optimal substructure: the max subarray ending at index `i` is either `nums[i]` itself or `nums[i] +` the max subarray ending at `i-1`. This DP relationship is the core of Kadane's Algorithm.

</details>

---

**15. Symmetric Tree**
> **Problem:** Given the `root` of a binary tree, check whether it is a mirror of itself (i.e., symmetric around its center).
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/symmetric-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS or BFS)**
  
  *   **The Clues (Why?):**
      *   You need to compare the `Tree`'s left side with its right side in a mirrored fashion.
      *   This requires a modified traversal where you compare two nodes at a time. A recursive DFS is very elegant: `isMirror(left_subtree, right_subtree)` checks if `left.val == right.val` and recursively calls `isMirror(left.left, right.right)` and `isMirror(left.right, right.left)`.

</details>

---

**16. Missing Number**
> **Problem:** Given an array `nums` containing `n` distinct numbers in the range `[0, n]`, return the only number in the range that is missing from the array.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/missing-number/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Math / Bit Manipulation (or Cyclic Sort)**
  
  *   **The Clues (Why?):**
      *   The problem guarantees a specific range of numbers `[0, n]`. This is a huge clue.
      *   **Math Approach:** You can calculate the expected sum of numbers from 0 to n using Gauss's formula `(n * (n+1)) / 2`. The missing number is simply `expected_sum - actual_sum`.
      *   **Cyclic Sort:** A more advanced but relevant pattern where you place each number at its correct index. The index that doesn't have its correct number is the missing one.

</details>

---

**17. Remove Duplicates from Sorted Array**
> **Problem:** Given an integer array `nums` sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   The array is **sorted**. This is a massive hint.
      *   The problem requires an **in-place** modification.
      *   You can use a "slow" pointer to track the position of the last unique element and a "fast" pointer to iterate through the array. When the fast pointer finds a new unique element, you place it at the slow pointer's next position.

</details>

---

**18. Path Sum**
> **Problem:** Given the `root` of a binary tree and an integer `targetSum`, return `true` if the tree has a root-to-leaf path such that adding up all the values along the path equals `targetSum`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/path-sum/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem asks to check if a **path exists**.
      *   It specifically mentions a **root-to-leaf** path, which implies exploring deep into the tree.
      *   DFS is the natural choice for path-finding problems. A recursive function can subtract the current node's value from the target sum and check the left and right children for the remaining sum.

</details>

---

**19. Move Zeroes**
> **Problem:** Given an integer array `nums`, move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/move-zeroes/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers**
  
  *   **The Clues (Why?):**
      *   The problem requires an **in-place** modification of an array.
      *   You can use a "slow" pointer to track the position where the next non-zero element should go. An iterator or "fast" pointer scans the array. When it finds a non-zero element, it places it at the slow pointer's position and increments the slow pointer.

</details>

---

**20. Majority Element**
> **Problem:** Given an array `nums` of size `n`, return the majority element. The majority element is the element that appears more than `⌊n / 2⌋` times.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/majority-element/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Hash Map (or Boyer-Moore Voting Algorithm)**
  
  *   **The Clues (Why?):**
      *   **Hash Map:** The problem asks you to count the **frequency** of elements. A hash map is the most straightforward way to store element counts and then find the one with the highest count.
      *   **Boyer-Moore:** This is a clever O(n) time, O(1) space algorithm. The guarantee that a majority element *always exists* is the key clue that a more optimized, specific algorithm can be used.

</details>

---

**21. Same Tree**
> **Problem:** Given the roots of two binary trees `p` and `q`, write a function to check if they are the same or not.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/same-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem requires comparing two `Trees` node by node.
      *   A recursive DFS is the simplest way to think about this. The base cases are when one or both nodes are null. The recursive step is to check if the current nodes' values are equal AND if their left subtrees are the same AND if their right subtrees are the same.

</details>

---

**22. Reverse Linked List**
> **Problem:** Given the `head` of a singly linked list, reverse the list, and return the reversed list.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/reverse-linked-list/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Two Pointers (or Three Pointers)**
  
  *   **The Clues (Why?):**
      *   This is a fundamental `Linked List` manipulation problem.
      *   The iterative solution requires keeping track of the `previous`, `current`, and sometimes `next` nodes as you traverse the list and reverse the direction of the pointers. This is a classic pointer manipulation pattern.

</details>

---

**23. Diameter of Binary Tree**
> **Problem:** Given the `root` of a binary tree, return the length of the diameter of the tree. The diameter is the length of the longest path between any two nodes in a tree.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/diameter-of-binary-tree/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Tree Traversal (DFS)**
  
  *   **The Clues (Why?):**
      *   The problem asks for the **"longest path"** in a `Tree`.
      *   The key insight is that for any node, the longest path passing through it is the `height of its left subtree + height of its right subtree`.
      *   This requires a post-order DFS traversal where you calculate the height of each subtree and simultaneously update a global variable for the maximum diameter found so far.

</details>

---

**24. Assign Cookies**
> **Problem:** Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie. Each child `i` has a greed factor `g[i]`, and each cookie `j` has a size `s[j]`. If `s[j] >= g[i]`, we can assign the cookie `j` to the child `i`. Your goal is to maximize the number of your content children.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/assign-cookies/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Greedy**
  
  *   **The Clues (Why?):**
      *   The problem asks you to **maximize** a value (the number of content children).
      *   There's a clear **locally optimal choice**: to satisfy the child with the *smallest greed factor*, it's always best to give them the *smallest cookie* that can satisfy them.
      *   By sorting both the greed factors and the cookie sizes, you can iterate through them and make this greedy choice at each step, which leads to the global optimum.

</details>

---

**25. Find All Numbers Disappeared in an Array**
> **Problem:** Given an array `nums` of `n` integers where `nums[i]` is in the range `[1, n]`, return an array of all the integers in the range `[1, n]` that do not appear in `nums`.
>
> **Link:** [LeetCode Problem](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/)

<details>
  <summary><strong>Click to Reveal Pattern & Clues</strong></summary>
  
  *   **Primary Pattern:** **Cyclic Sort (or in-place marking)**
  
  *   **The Clues (Why?):**
      *   The problem states the numbers are in a specific range `[1, n]`, which is the same as the array's indices (plus or minus one). This is the biggest clue for a Cyclic Sort style of problem.
      *   The goal is to find missing numbers without using extra space. The clever trick is to use the array itself as a hash map. You can iterate through the array and mark the index corresponding to each number you see (e.g., by making the number at that index negative). In a second pass, any index whose number is still positive is a missing number.

</details>
