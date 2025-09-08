---
markmap:
  colorScheme: 'indigo'
---

# The Playbook: Fast & Slow Pointers

## 💡 The Big Idea
- A specific variant of the Two Pointers technique, almost exclusively used for problems involving **Linked Lists**.
- It uses two pointers that traverse the list at different speeds.
- **Core Idea:** The different speeds of the pointers inevitably lead them to a specific state (e.g., meeting, one reaching the end) that reveals a key property of the list.

## 🔍 When to Use It? (Problem Clues)
- The problem involves a **Linked List**.
- You need to find...
  - if the list has a **"cycle"**.
  - the **"middle node"** of the list.
  - the **"start of the cycle"**.
  - a specific **"k-th node from the end"**.

## 🛠️ The Game Plan: The Hare and the Tortoise 🐢🐇

### The Core Mechanism
- **Slow Pointer:** Moves one step at a time. (`slow = slow.next`)
- **Fast Pointer:** Moves two steps at a time. (`fast = fast.next.next`)
- Both pointers start at the head of the list.

## ⚙️ Common Applications & Templates

### 1. Cycle Detection
- **Problem:** "Does the linked list have a cycle?"
- **The Logic:**
  - If the list is linear (no cycle), the `fast` pointer will always reach the end (`null`) first.
  - If there is a cycle, the `fast` pointer will eventually "lap" the `slow` pointer, and they will meet at some node inside the cycle.
- **Template:**
  ```
  slow = head, fast = head
  while (fast != null and fast.next != null):
    slow = slow.next
    fast = fast.next.next
    if (slow == fast):
      return true // Cycle detected
  return false // No cycle
  ```

### 2. Finding the Middle of a Linked List
- **Problem:** "Find the middle node of the linked list."
- **The Logic:**
  - When the `fast` pointer reaches the end of the list, the `slow` pointer will be exactly at the middle.
- **Template:**
  ```
  slow = head, fast = head
  while (fast != null and fast.next != null):
    slow = slow.next
    fast = fast.next.next
  return slow // slow is now at the middle
  ```

### 3. Finding the Start of a Cycle
- **Problem:** "Given a cyclic list, find the node where the cycle begins."
- **The Logic (Floyd's Cycle-Finding Algorithm):**
  1.  **Step 1:** Find the meeting point using the standard cycle detection method above.
  2.  **Step 2:** Reset one pointer (e.g., `slow`) back to the `head`. Keep the other pointer (`fast`) at the meeting point.
  3.  **Step 3:** Move both pointers one step at a time. The node where they meet again is the start of the cycle.

## 经典蓝图 (Classic Blueprints)
- **Easy:**
  - [Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
  - [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
- **Medium:**
  - [Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/) (Find the start of the cycle)
  - [Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/) (Hint: Find the middle, then reverse the second half)
