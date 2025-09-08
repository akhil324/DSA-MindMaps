

# The Core Toolkit: Linear Structures

## 🧱 Arrays
- **Core Idea:** A fixed-size list of items stored in a single, contiguous block of memory. Like a numbered row of parking spots.
- **Pros:**
  - **Fast Random Access (O(1)):** You can jump to any "parking spot" instantly if you know its number (index).
- **Cons:**
  - **Fixed Size:** You must decide the size upfront. Resizing is expensive (O(n)).
  - **Slow Insertion/Deletion (O(n)):** Adding or removing an item in the middle requires shifting all other items.
- **Operations & Big O:**
  - `Read (by index)`: O(1)
  - `Insert (at end)`: O(1) (amortized)
  - `Insert (at beginning/middle)`: O(n)
  - `Delete`: O(n)
  - `Search`: O(n)
- **Key Algorithms & Patterns:**
  - **Binary Search:** (Requires a **sorted** array)
  - **Two Pointers:** Very common for array problems.
  - **Sliding Window:** For problems on contiguous subarrays.

## 🔗 Linked Lists
- **Core Idea:** A chain of nodes where each node contains data and a pointer to the next node. Like a treasure hunt where each clue leads to the next.
- **Pros:**
  - **Dynamic Size:** Can grow or shrink easily.
  - **Fast Insertion/Deletion (O(1)):** If you are already at the node, you just need to change a few pointers.
- **Cons:**
  - **Slow Access & Search (O(n)):** To find the 5th item, you must start at the head and follow the chain 4 times.
  - **Extra Memory:** Each node needs extra space for its pointer(s).
- **Types:**
  - **Singly:** Each node points forward only.
  - **Doubly:** Each node points forward and backward.
- **Operations & Big O:**
  - `Read (by index)`: O(n)
  - `Search`: O(n)
  - `Insert (at beginning)`: O(1)
  - `Insert (at end)`: O(n) without tail pointer, O(1) with.
  - `Delete`: O(1) (if you have the node)
- **Key Algorithms & Patterns:**
  - **Two Pointers:** (e.g., finding the middle node)
  - **Fast & Slow Pointers:** (e.g., detecting a cycle)

## 🥞 Stacks (LIFO)
- **Core Idea:** A "Last-In, First-Out" structure. The last item you add is the first one you can remove. Like a stack of plates.
- **Implementation:**
  - Can be built using an **Array** or a **Linked List**.
- **Pros:**
  - Provides a simple, structured way to handle certain problems (e.g., reversing things, managing function calls).
- **Cons:**
  - Limited access; you can only interact with the top element.
- **Operations & Big O:**
  - `Push (add to top)`: O(1)
  - `Pop (remove from top)`: O(1)
  - `Peek (view top)`: O(1)
- **Key Use Cases:**
  - **Function Call Stack:** Managing function execution.
  - **Undo/Redo:** The last action is the first to be undone.
  - **Expression Evaluation:** (e.g., checking for balanced parentheses)

## 🎟️ Queues (FIFO)
- **Core Idea:** A "First-In, First-Out" structure. The first item you add is the first one you can remove. Like a line at a ticket counter.
- **Implementation:**
  - Can be built using an **Array** (circular) or a **Linked List**.
- **Pros:**
  - Fair way to process tasks in the order they were received.
- **Cons:**
  - Limited access; you can only add to the back and remove from the front.
- **Operations & Big O:**
  - `Enqueue (add to back)`: O(1)
  - `Dequeue (remove from front)`: O(1)
  - `Peek (view front)`: O(1)
- **Key Use Cases:**
  - **Breadth-First Search (BFS):** The core data structure for BFS in trees and graphs.
  - **Task Scheduling:** Processing tasks in order.
  - **Buffering:** Handling data streams.
