

# The Playbook: Dynamic Programming (DP)

## 💡 The Big Idea
- A method for solving complex problems by breaking them down into simpler, **overlapping subproblems**.
- The key is to solve each subproblem **only once** and store its result.
- **Core Principle:** "Don't Repeat Yourself." If you've calculated something before, just look up the answer instead of re-computing it.

## 🔍 When to Use It? (Problem Clues)
- The problem asks for the **maximum/minimum value**, the **number of ways** to do something, or to find if a solution is **possible**.
- The problem has two key properties:
  1.  **Optimal Substructure:** The optimal solution to the main problem can be constructed from the optimal solutions of its subproblems.
  2.  **Overlapping Subproblems:** A recursive solution would solve the same subproblems over and over again.

## 🛠️ The Game Plan: Two Main Approaches

### 1. Memoization (Top-Down)
- **Core Idea:** "Remember your past."
- **How it Works:**
  - Write a standard recursive solution.
  - Add a cache (like a hash map or an array) to store the results of subproblems.
  - Before computing a result, check if it's already in the cache. If yes, return it. If no, compute it, store it in the cache, and then return it.
- **Analogy:** Doing an open-book exam. You try to solve a problem, but if you've already solved an identical one, you just copy the answer from your notes.

### 2. Tabulation (Bottom-Up)
- **Core Idea:** "Build from the ground up."
- **How it Works:**
  - Create a table (usually a 1D or 2D array), often called `dp`.
  - The size of the table corresponds to the inputs of the problem.
  - Fill the table iteratively, starting with the base cases.
  - Each entry `dp[i]` is calculated using previously computed values (e.g., `dp[i-1]`, `dp[i-2]`).
  - The final answer is the last entry in the table.
- **Analogy:** Building a wall brick by brick. You can't place a brick on top until the one below it is already there.

## Memoization vs. Tabulation
- **Memoization:** Often more intuitive to write (closer to the recursive thought process).
- **Tabulation:** Can be more space-efficient and avoids recursion depth limits.

## Classic Blueprints
- **Easy:**
  - [Fibonacci Number](https://leetcode.com/problems/fibonacci-number/)
  - [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)
- **Medium:**
  - [Coin Change](https://leetcode.com/problems/coin-change/)
  - [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)
  - [0/1 Knapsack Problem](https://www.geeksforgeeks.org/0-1-knapsack-problem-dp-10/)
  - [House Robber](https://leetcode.com/problems/house-robber/)
