

# The Playbook: Greedy Algorithms

## 💡 The Big Idea
- A strategy for solving optimization problems by making the **locally optimal choice** at each stage with the hope of finding a **global optimum**.
- **Core Idea:** "What's the best move I can make *right now*?"
- It doesn't worry about the future consequences of its choices; it just picks the best immediate option.

## 🔍 When to Use It? (Problem Clues)
- The problem is an **optimization problem** (find the maximum, minimum, or optimal solution).
- It feels like you can build a solution piece by piece, and the choice at each step is clear and simple.
- You can identify a "greedy choice property": a locally optimal choice leads to a globally optimal solution.
- **Warning:** The hardest part is **proving** that a greedy approach actually works for a given problem.

## 🛠️ The Game Plan: The Greedy Choice
- **Core Logic:**
  1.  Identify what a "greedy choice" means for the problem (e.g., picking the smallest item, the item that finishes earliest, the most valuable item).
  2.  Create a loop that repeatedly makes this greedy choice.
  3.  With each choice, reduce the problem to a smaller subproblem.
  4.  Continue until the problem is solved.

## ✅ When It Works vs. ❌ When It Fails

### ✅ Works: Optimal Substructure
- The problem can be broken down, and an optimal solution to the whole problem contains optimal solutions to its subproblems.
- **Example: Coin Change (with standard coin sets)**
  - To make change for 49 cents, you greedily pick a quarter (25). Now you have a smaller subproblem: making change for 24 cents. The optimal solution for 24 cents, combined with your quarter, gives the global optimum.

### ❌ Fails: When the Local Choice Isn't Globally Best
- The best immediate choice might prevent you from making a much better choice later.
- **Example: 0/1 Knapsack Problem**
  - You have a knapsack with a weight limit. You can't just greedily pick the most valuable item, because it might be very heavy and fill up your whole bag, preventing you from picking several other items that are slightly less valuable but have a much higher combined value.
  - **(This is a classic DP problem, not a greedy one!)**

## Classic Blueprints
- **Easy:**
  - [Assign Cookies](https://leetcode.com/problems/assign-cookies/)
- **Medium:**
  - [Jump Game](https://leetcode.com/problems/jump-game/)
  - [Gas Station](https://leetcode.com/problems/gas-station/)
  - [Merge Intervals](https://leetcode.com/problems/merge-intervals/) (Sorting first is the greedy choice)
  - [Minimum Platforms](https://www.geeksforgeeks.org/problems/minimum-platforms-1587115620/1)
