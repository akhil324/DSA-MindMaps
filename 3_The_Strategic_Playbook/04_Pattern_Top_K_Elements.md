

# The Playbook: Top K Elements

## 💡 The Big Idea
- A pattern to efficiently find the top `k` largest, smallest, or most frequent elements in a collection.
- While sorting the entire collection works, it's often inefficient. This pattern provides a more optimal solution.

## 🔍 When to Use It? (Problem Clues)
- The problem explicitly asks for the...
  - **"top `k` elements"**
  - **"`k`th largest/smallest element"**
  - **"`k` most frequent elements"**
  - **"`k` closest points"** to an origin.

## 🛠️ The Game Plan: Heap is the Hero

### The Brute-Force Approach (Don't Do This in an Interview)
- **Method:** Sort the entire array.
- **Action:** Take the first `k` or last `k` elements.
- **Complexity:** **O(n log n)**. It's too slow because you are sorting elements you don't care about.

### The Optimal Approach (The Heap Method)
- **Key Data Structure:** A **Min-Heap** or a **Max-Heap** of size `k`.
- **Core Idea:** Maintain a heap of size `k` and iterate through the list. By the end, the heap will contain the `k` elements you're looking for.
- **Complexity:** **O(n log k)**. This is much better than O(n log n) when `k` is smaller than `n`.

## ⚙️ Template: Finding the `k` Largest Elements
- **Tool:** Use a **Min-Heap** of size `k`.
- **Why a Min-Heap?**
  - The heap's root is always the *smallest* of the `k` largest elements found so far.
  - This makes it easy to decide if a new, larger element belongs in the top `k` set.
- **The Algorithm:**
  1. Create a Min-Heap.
  2. Iterate through the first `k` elements of the array and add them to the heap.
  3. For the rest of the elements (`k` to `n`):
     - If the current element is **larger** than the root of the heap (`heap.peek()`):
       - Remove the root (`heap.poll()`).
       - Add the current element to the heap (`heap.add(element)`).
  4. After the loop, the heap contains the `k` largest elements.

## Classic Blueprints
- **Easy/Medium:**
  - [Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/)
- **Medium:**
  - [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
  - [K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/)
  - [Find K Largest Elements in an Array](https://www.geeksforgeeks.org/problems/k-largest-elements4206/1)
