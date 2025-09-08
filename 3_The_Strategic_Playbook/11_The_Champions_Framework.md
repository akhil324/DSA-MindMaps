

# The Playbook: The Champion's Framework

## 💡 The Big Idea
- Acing a coding interview is not just about knowing the answer. It's about demonstrating a structured, professional problem-solving process.
- This framework is a step-by-step guide to confidently navigate any coding problem, from understanding to optimization.

## 🏆 The Framework: A 6-Step Process

### 1. Clarify & Understand (Listen First) 👂
- **Goal:** Make sure you 100% understand the problem before writing a single line of code.
- **Actions:**
  - **Repeat the problem back** in your own words.
  - **Ask clarifying questions** about:
    - **Inputs:** What is the data type? (array, string, etc.). Are there negative numbers? Duplicates? Is it sorted?
    - **Outputs:** What should the function return? (a number, a list, a boolean?).
    - **Constraints & Edge Cases:** What if the input is empty, null, or very large?
  - **"Never assume, always clarify."**

### 2. Create Examples (Test Your Understanding) 🧪
- **Goal:** Solidify your understanding and create test cases for your future solution.
- **Actions:**
  - **Simple Case:** A standard, straightforward example.
  - **Complex Case:** A more involved example that tests multiple parts of the logic.
  - **Edge Cases:** Empty inputs, single-element inputs, inputs with duplicates.
  - **Invalid Inputs:** What should happen if the input is `null`?

### 3. Brute-Force Solution (The First Draft) 🧠
- **Goal:** Get a working solution on the board, even if it's inefficient. This shows you can solve the problem.
- **Actions:**
  - **Verbalize your approach first.** "My initial thought is to use a nested loop, which would be O(n²)..."
  - This is often the most obvious solution (e.g., nested loops, generating all possibilities).
  - **Analyze its complexity:** "This works, but the time complexity is O(n²), and we can probably do better."

### 4. Optimize (The Masterstroke) ✨
- **Goal:** Improve upon the brute-force solution. This is where you show off your DSA knowledge.
- **Actions:**
  - **Identify the Bottleneck:** What part of the brute-force solution is slow? (e.g., the nested loop, re-computation).
  - **Apply a Pattern!** "To get rid of the nested loop, I can use the **Sliding Window** pattern..." or "A **Hash Map** could help me store seen values for an O(1) lookup..."
  - **Discuss Trade-offs:** "Using a hash map will improve my time complexity to O(n), but it will require O(n) extra space."

### 5. Code (The Implementation) 💻
- **Goal:** Write clean, readable, and correct code for your optimized solution.
- **Actions:**
  - **Talk as you code.** Explain what you're doing and why.
  - Use meaningful variable names.
  - Structure your code logically.

### 6. Test & Verify (The Final Check) ✅
- **Goal:** Prove your code works using the examples you created earlier.
- **Actions:**
  - **Dry Run:** Manually walk through your code with one of your test cases.
  - Track the state of your variables.
  - Verbally confirm that the output matches your expected result.
  - Discuss any final edge cases you might have missed.
