

# The Sorting Workshop

## Simple (but slow) Methods - O(n²)

### Bubble Sort 🫧
- **Core Idea:** "Bubble" the largest elements to the end by repeatedly swapping adjacent items if they are in the wrong order.
- **How it Works:**
  1. Iterate through the array from the beginning.
  2. Compare each element with the one next to it.
  3. If `arr[i] > arr[i+1]`, swap them.
  4. Repeat `n` times. The largest elements "bubble up" to the right.
- **Complexity:**
  - **Time:** O(n²) - (Very slow for large datasets)
  - **Space:** O(1) - (In-place)
- **Use Case:** Mostly educational. Rarely used in practice.

### Selection Sort ☑️
- **Core Idea:** Find the smallest element in the unsorted part of the list and "select" it to be placed at the beginning.
- **How it Works:**
  1. Assume the first element is the smallest.
  2. Iterate through the rest of the array to find the *true* smallest element.
  3. Swap the true smallest element with the first element.
  4. Repeat for the second, third, etc., positions.
- **Complexity:**
  - **Time:** O(n²) - (Slow, but consistent performance)
  - **Space:** O(1) - (In-place)
- **Use Case:** Good when memory writes are expensive, as it minimizes swaps.

### Insertion Sort 🃏
- **Core Idea:** Build the final sorted array one item at a time. Like sorting a hand of playing cards.
- **How it Works:**
  1. Start with the second element.
  2. Compare it to the elements before it and "insert" it into its correct sorted position.
  3. Repeat for all other elements.
- **Complexity:**
  - **Time:** O(n²) - (Worst case) | O(n) - (Best case, if nearly sorted)
  - **Space:** O(1) - (In-place)
- **Use Case:** Very efficient for small or nearly-sorted datasets.

## Efficient (and practical) Methods - O(n log n)

### Merge Sort 🤝
- **Core Idea:** "Divide and Conquer." Break the array down into single elements, then merge them back together in sorted order.
- **How it Works:**
  1. **Divide:** Recursively split the array in half until you have arrays of size 1.
  2. **Conquer:** Merge the smaller arrays back together. When merging, compare elements from the two arrays and place the smaller one into the new array.
- **Complexity:**
  - **Time:** O(n log n) - (Reliable and consistent)
  - **Space:** O(n) - (Requires extra space for merging)
- **Use Case:** The go-to for stable, reliable sorting.

### Quick Sort ⚡
- **Core Idea:** "Divide and Conquer." Pick a "pivot" element and partition the array so that all smaller elements are to its left and all larger elements are to its right.
- **How it Works:**
  1. **Choose a Pivot:** (e.g., the last element).
  2. **Partition:** Rearrange the array so elements `< pivot` are on the left, and elements `> pivot` are on the right. The pivot is now in its final sorted position.
  3. **Recurse:** Apply Quick Sort to the left and right subarrays.
- **Complexity:**
  - **Time:** O(n log n) - (Average case) | O(n²) - (Worst case, if pivot is bad)
  - **Space:** O(log n) - (Uses the call stack for recursion)
- **Use Case:** Often the fastest in practice due to good cache performance. Many standard library sort functions use a variation of it.
