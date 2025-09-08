---
markmap:
  colorScheme: 'orange'
---

# The Playbook: Two Pointers Pattern

## 💡 The Big Idea
- A powerful technique that uses two pointers to iterate through a data structure (usually a **sorted array** or **linked list**) until they meet or satisfy a condition.
- By moving the pointers intelligently, we can process the data in a single pass, avoiding the need for nested loops.
- **Result:** Turns many O(n²) brute-force solutions into optimal **O(n)** or **O(n log n)** solutions.

## 🔍 When to Use It? (Problem Clues)
- The problem involves a **sorted array** (or a pair of sorted arrays), a **string**, or a **linked list**.
- You are looking for a **pair**, a **triplet**, or a **subarray** that fulfills a certain condition.
- The problem involves **reversing**, **comparing**, or finding a **specific point** in the data.

## 🛠️ The Game Plan: Common Variations

### 1. Converging Pointers (Opposite Ends)
- **Use Case:** On a **sorted array**, when you need to find a pair of values that meet a target.
- **Pointer Movement:** One pointer starts at the `beginning` (`left`), and the other starts at the `end` (`right`). They move **towards each other**.
- **Example Problem:** "Given a sorted array, find a pair that sums up to a target value."
- **The Template:**
  ```
  left = 0, right = array.length - 1
  while (left < right):
    currentSum = array[left] + array[right]
    if (currentSum == target):
      // Found it!
      return [left, right]
    else if (currentSum < target):
      // Sum is too small, need a larger number
      left++
    else: // currentSum > target
      // Sum is too big, need a smaller number
      right--
  ```

### 2. Fast & Slow Pointers (Same Direction)
- **Use Case:** Dealing with **linked lists** to find cycles, middle elements, or specific nodes.
- **Pointer Movement:** Both pointers start at the `head`. The `slow` pointer moves one step at a time (`slow = slow.next`), while the `fast` pointer moves two steps (`fast = fast.next.next`).
- **Example Problem:** "Detect if a linked list has a cycle."
- **The Logic:** If there is a cycle, the `fast` pointer will eventually lap the `slow` pointer and they will meet. If `fast` reaches the end (`null`), there is no cycle.

## 经典蓝图 (Classic Blueprints)
- **Easy:**
  - [Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
  - [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)
  - [Reverse String](https://leetcode.com/problems/reverse-string/)
- **Medium:**
  - [3Sum](https://leetcode.com/problems/3sum/) (Often involves sorting then using two pointers within a loop)
  - [Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
  - [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/) (Fast & Slow variant)

