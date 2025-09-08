---
markmap:
  colorScheme: 'indigo'
---

# The Playbook: Modified Binary Search

## 💡 The Big Idea
- An advanced application of the classic Binary Search algorithm.
- It's used on data that isn't a simple sorted array but still has a predictable, ordered property that we can exploit.
- **Core Idea:** Instead of searching for a specific value, you are often searching for a **boundary condition** or the **minimum/maximum value** that satisfies a condition.

## 🔍 When to Use It? (Problem Clues)
- The problem involves a **sorted array that has been rotated**.
- The problem asks you to find the **peak** or **minimum element** in a cyclically sorted array.
- The problem has a **monotonic property**: as you increase a potential answer, the result either consistently increases or decreases (e.g., "Can we achieve this with a speed of `x`?"). This allows you to binary search on the *answer itself*.

## 🛠️ The Game Plan: Find the Sorted Part

### The Core Challenge
- In a standard sorted array, if `mid` is not the target, you always know whether to go left or right.
- In a **rotated sorted array**, this is no longer true. The key is to first identify which half of the array (`left` to `mid` or `mid` to `right`) is still properly sorted.

## ⚙️ Template: Searching in a Rotated Sorted Array
```
left = 0, right = array.length - 1

while (left <= right):
  mid = left + (right - left) / 2

  if (array[mid] == target):
    return mid

  // 1. Check if the left half is sorted
  if (array[left] <= array[mid]):
    // 2. Check if the target is within the sorted left half's range
    if (target >= array[left] and target < array[mid]):
      right = mid - 1 // Go left
    else:
      left = mid + 1  // Go right
  
  // 3. Otherwise, the right half must be sorted
  else:
    // 4. Check if the target is within the sorted right half's range
    if (target > array[mid] and target <= array[right]):
      left = mid + 1   // Go right
    else:
      right = mid - 1 // Go left
```

## 经典蓝图 (Classic Blueprints)
- **Medium:**
  - [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)
  - [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)
  - [Find Peak Element](https://leetcode.com/problems/find-peak-element/)
- **Hard:**
  - [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) (Binary searching on the partition)
  - [Split Array Largest Sum](https://leetcode.com/problems/split-array-largest-sum/) (Binary searching on the answer)
