---
markmap:
  colorScheme: 'orange'
---

# The Playbook: Sliding Window Pattern

## 💡 The Big Idea
- To efficiently process a **contiguous** part of a linear data structure (like an Array or String).
- Imagine a "window" of a certain size that **slides** over the data.
- Instead of re-calculating everything for each new position (the O(n²) brute-force way), we cleverly **add** the new element and **subtract** the old one.
- **Result:** Turns many O(n²) problems into optimal **O(n)** solutions.

## 🔍 When to Use It? (Problem Clues)
- The problem involves an **Array** or a **String**.
- You are asked to find the **longest**, **shortest**, or **maximum/minimum value** of a...
  - **"contiguous subarray"**
  - **"substring"**
- The problem mentions a **fixed size `k`** or a constraint that can be used to define the window size (e.g., "at most k distinct characters").

## 🛠️ The Game Plan: Two Main Variations

### 1. Fixed Size Window
- **Use Case:** The problem gives you a fixed window size, `k`.
- **Example Problem:** "Find the maximum sum of any contiguous subarray of size `k`."
- **The Template:**
  ```
  // 1. Calculate the sum of the first window of size k
  // 2. Initialize maxSum with this first sum
  // 3. Loop from the k-th element to the end of the array:
  //    a. Add the new element to the window sum
  //    b. Subtract the element that just fell out of the window
  //    c. Update maxSum
  ```

### 2. Dynamic Size Window
- **Use Case:** The window size changes based on a condition (e.g., "sum is less than X", "contains at most 2 distinct characters").
- **Example Problem:** "Find the length of the longest substring with no more than `k` distinct characters."
- **The Template (using two pointers, `start` and `end`):**
  ```
  // 1. Initialize windowStart = 0, maxLength = 0
  // 2. Loop with windowEnd from 0 to the end of the array:
  //    a. Add the element at windowEnd to the window
  // 3.  While the window is no longer valid (e.g., > k distinct chars):
  //       a. Shrink the window from the left:
  //          - Remove the element at windowStart
  //          - Increment windowStart
  //    b. Update maxLength
  ```

## 经典蓝图 (Classic Blueprints)
- **Easy:**
  - [Maximum Sum Subarray of Size K](https://leetcode.com/problems/maximum-subarray/) (Note: LeetCode's classic version is slightly different, but the fixed-window concept applies)
- **Medium:**
  - [Longest Substring with K Distinct Characters](https://leetcode.com/problems/longest-substring-with-at-most-k-distinct-characters/)
  - [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
  - [Permutation in a String](https://leetcode.com/problems/permutation-in-string/)

