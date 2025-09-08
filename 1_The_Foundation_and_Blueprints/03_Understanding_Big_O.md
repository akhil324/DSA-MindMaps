---
markmap:
  colorScheme: 'teal'
---

# Measuring Success: Understanding Big O

## 🤔 What is Big O?
- A way to describe how the **runtime** (Time Complexity) or **memory usage** (Space Complexity) of an algorithm grows as the input size (`n`) gets larger.
- **It's about the TREND, not the exact time.**
- **Analogy: Delivering a Package**
  - `n` = number of houses on a street.
  - How long does your delivery route take as `n` grows?

## 📈 The Big O Hierarchy (Best to Worst)

### O(1) - Constant Time
- **The Dream Scenario**
- The runtime is the **same** no matter how big the input is.
- **Analogy:** Your delivery is to the **first house** on the street. It doesn't matter if there are 10 or 1000 houses; the time is the same.
- **Code Example:** Accessing an element in an array by its index (`my_array[5]`).

### O(log n) - Logarithmic Time
- **Extremely Efficient**
- The runtime grows very slowly. Every time you double the input size, you only do one more step.
- **Analogy:** Finding a name in a phone book. You open to the middle, decide which half to look in, and repeat. You cut the problem in half with each step.
- **Code Example:** **Binary Search** on a sorted array.

### O(n) - Linear Time
- **Fair and Common**
- The runtime grows **directly proportional** to the input size. If you double the input, you double the work.
- **Analogy:** You have to deliver a package to **every single house** on the street. 100 houses = 100 stops.
- **Code Example:** Looping through all elements in an array once.

### O(n log n) - "Log-Linear" Time
- **The Sorting Sweet Spot**
- A very common and efficient complexity for sorting algorithms.
- **Analogy:** A more complex delivery where for each of the `n` houses, you have to do a "phone book lookup" (a `log n` operation).
- **Code Example:** Efficient sorting algorithms like **Merge Sort** and **Quick Sort**.

### O(n²) - Quadratic Time
- **Getting Slow** 🐢
- The runtime grows by the square of the input size. If `n` is 10, runtime is ~100. If `n` is 100, runtime is ~10,000.
- **Analogy:** You have to visit every house, and at each house, you have to shout the name of every other resident on the street.
- **Code Example:** A **nested loop** where you iterate over the same collection twice (`for i in list: for j in list:`).

### O(2ⁿ) - Exponential Time
- **The Danger Zone** ☠️
- The runtime doubles with every single new element added to the input. Becomes unusable very quickly.
- **Analogy:** Trying to guess a password. For each character, you double the number of combinations you have to check.
- **Code Example:** Recursive calculation of Fibonacci numbers (the naive way).

## 💡 Key Takeaways
- **Focus on the Worst Case:** We usually care about the worst-case scenario to guarantee performance.
- **Drop Constants & Non-Dominant Terms:** O(2n + 100) is just **O(n)**. We only care about the term that grows the fastest.
