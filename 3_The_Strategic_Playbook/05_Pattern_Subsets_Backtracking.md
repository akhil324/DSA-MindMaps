---
markmap:
  colorScheme: 'orange'
---

# The Playbook: Subsets & Backtracking

## 💡 The Big Idea
- A powerful pattern for problems that require generating **all possible solutions** and choosing the ones that fit a certain criteria.
- It systematically explores all potential combinations, permutations, or paths.

## 🔍 When to Use It? (Problem Clues)
- The problem asks you to find...
  - **"all possible subsets"**
  - **"all possible permutations"**
  - **"all possible combinations"**
  - **"all valid paths"**
- The problem involves making a sequence of choices, and a bad choice can be undone.

## 🛠️ The Core Concept: Backtracking
- **Analogy:** Exploring a maze.
  1.  You come to a fork in the road and **choose** a path.
  2.  You **explore** that path as far as you can.
  3.  If you hit a dead end, you **"backtrack"** to the fork and try the other path.
- **The "Choose, Explore, Unchoose" Cycle:**
  - **Choose:** Add an element to your current solution set.
  - **Explore:** Make a recursive call with the updated set to find further solutions.
  - **Unchoose:** **(This is the key!)** Remove the element you just added, so you can explore other paths from the same decision point.

## ⚙️ The Game Plan: A Recursive Template

### Template for Generating Subsets
```
function findSubsets(inputArray):
  allSubsets = []
  currentSubset = []

  function backtrack(startIndex):
    // 1. Add the current state as a valid solution
    allSubsets.add(copy of currentSubset)

    // 2. Explore further choices
    for i from startIndex to end of inputArray:
      // a. Choose
      currentSubset.add(inputArray[i])

      // b. Explore
      backtrack(i + 1)

      // c. Unchoose (Backtrack)
      currentSubset.removeLast()

  backtrack(0)
  return allSubsets
```

## 经典蓝图 (Classic Blueprints)
- **Medium:**
  - [Subsets](https://leetcode.com/problems/subsets/)
  - [Permutations](https://leetcode.com/problems/permutations/)
  - [Combination Sum](https://leetcode.com/problems/combination-sum/)
  - [Generate Parentheses](https://leetcode.com/problems/generate-parentheses/)
- **Hard:**
  - [N-Queens](https://leetcode.com/problems/n-queens/)
