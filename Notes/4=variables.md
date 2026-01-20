Welcome to Introduction to Computer Science. Please, take a seat.

Today, we are going to ignore the complex screens, the flashing lights, and the buzzwords like "Artificial Intelligence" or "Cloud Computing." We are going to start at the absolute bottom.

We are going to talk about **Variables and Assignment**.

### 1. The Problem: Why do we need this?

Imagine you are cooking a complex dinner. You have a knife, a cutting board, and ingredients. You chop an onion. Now, you need to chop a carrot.

What do you do with the chopped onion? You cannot keep holding it in your hand while you chop the carrot. You need to put it somewhere—a bowl, a plate, or a pan—so you can use it later.

Without a place to store the result of your work (the chopped onion), you cannot proceed to the next step.

Computers have the exact same problem. A computer is essentially a calculator that runs extremely fast. It calculates a number. If it doesn't save that number immediately, the number vanishes. It’s gone.

To build a program, we need a way to tell the computer: *"Calculate this result, give it a name, and hold onto it until I ask for it."*

That is what a **Variable** is.

---

### 2. The Mental Model: Labels and Boxes

In mathematics, you might recall seeing something like this:
$$x = 5$$

In algebra, this means "$x$ is equal to 5." It is a statement of fact.

In Computer Science, we use similar notation, but the meaning is entirely different. In Python, when we write:

```python
x = 5
```

We are not stating a fact. We are giving a **command**.

Here is the analogy I want you to keep in your head: **Computer Memory is a giant warehouse filled with empty cardboard boxes.**

When you write `x = 5`, you are telling the warehouse manager (the computer) to do three things, in this specific order:
1.  Find an empty box.
2.  Put the number **5** inside that box.
3.  Take a sticky note, write **"x"** on it, and slap it on the outside of the box.

Now, whenever you ask for `x`, the manager looks for the box with the "x" sticker and gives you what is inside.

### 3. The Syntax: The Assignment Operator

In Python, the equals sign (`=`) is not called "equals." It is called the **Assignment Operator**.

This is the most important rule of the day. Read the `=` sign as an arrow pointing to the left:

$$ \leftarrow $$

The flow of logic **always** moves from Right to Left.

```python
variable_name = data
```

**Step 1:** The computer looks at the right side and prepares the data.
**Step 2:** The computer saves that data into the name provided on the left side.

---

### 4. Examples: From Simple to Complex

Let's look at how this works in practice.

#### Level 1: Creating a Variable
```python
score = 10
```
*   **Computer's thought process:** "Okay, the human wants to store the number 10. I will create a space in memory and label it `score`."

#### Level 2: Retrieving a Variable
```python
print(score)
```
*   **Computer's thought process:** "The human wants to `print` (show on screen) something. They used the word `score`. Let me go check the warehouse. Ah, here is the box labeled `score`. Inside is the number 10. I will display 10."

#### Level 3: Re-assignment (Changing the value)
This is where programming diverges from math. In math, if $x=5$, $x$ is always 5. In programming, variables can change. That is why they are called *vari-ables* (able to vary).

```python
score = 10
print(score)  # Prints 10

score = 20
print(score)  # Prints 20
```
*   **Computer's thought process on the third line:** "The human is using the `score` label again. They want to put `20` into it. I will take the `10` out of the box, throw it away, and put `20` in there instead."

#### Level 4: The "Mind-Bender"
This is the concept that usually trips up beginners. Look at this code:

```python
score = 10
score = score + 1
```

If you look at this like a math equation ($x = x + 1$), it is impossible. $10$ cannot equal $11$.
But remember, **Right to Left**.

Let's do a **Dry Run** (a mental simulation) of that second line: `score = score + 1`.

1.  **Cover the left side.** Ignore `score =` for a moment. Look only at the right: `score + 1`.
2.  **Retrieve.** The computer looks inside the box labeled `score`. It finds `10`.
3.  **Calculate.** The computer calculates `10 + 1`. The result is `11`.
4.  **Assign.** Now, the computer looks at the left side: `score =`. It takes that new result (`11`) and stores it back in the box labeled `score`, overwriting the old number.

The value of `score` is now 11.

---

### 5. Common Beginner Mistakes

There are three mistakes almost everyone makes in their first week.

**Mistake 1: The Reverse Assignment**
```python
10 = score
```
*   **Why it fails:** Remember the rule? Right to Left. You are trying to take the value of `score` and stuff it inside the number 10. The number 10 is not a box; it's just a number. You cannot stick a label on the number 10. The variable name must always be on the left.

**Mistake 2: Naming is Case Sensitive**
```python
score = 5
print(Score)
```
*   **Why it fails:** To a computer, `score` (lowercase s) and `Score` (uppercase S) are two completely different boxes. The computer will look for the box labeled `Score`, not find it, and panic (throw an error).

**Mistake 3: Using a Variable Before Creating It**
```python
print(total)
total = 100
```
*   **Why it fails:** The computer executes code top-to-bottom. On line 1, you ask for `total`. The computer checks the warehouse, but you haven't created that box yet. It crashes. You must assign before you retrieve.

---

### 6. Practice Problems

To truly understand this, you must think like the machine. Grab a piece of paper and a pen. I want you to track the value of the variables step-by-step.

**Problem A:**
```python
a = 5
b = 10
a = b
b = 20
print(a)
```
*Question: What prints out?*

<details>
<summary><em>Click to reveal the professor's thinking</em></summary>
<strong>Answer: 10</strong><br>
Let's trace it:
1. <code>a</code> gets 5.
2. <code>b</code> gets 10.
3. <code>a = b</code>: The computer looks at <code>b</code> (which is 10) and copies that value into <code>a</code>. Now <code>a</code> is 10.
4. <code>b = 20</code>: The computer puts 20 into <code>b</code>. This does <strong>not</strong> affect <code>a</code>. <code>a</code> is still safe in its own box holding the 10 we gave it earlier.
</details>

<br>

**Problem B:**
```python
points = 50
bonus = 10
points = points + bonus
points = points - 5
print(points)
```
*Question: What prints out?*

<details>
<summary><em>Click to reveal the professor's thinking</em></summary>
<strong>Answer: 55</strong><br>
Trace it:
1. <code>points</code> is 50.
2. <code>bonus</code> is 10.
3. <code>points = points + bonus</code>: Right side first (50 + 10 = 60). Store 60 in <code>points</code>.
4. <code>points = points - 5</code>: Right side first. Look at <code>points</code> (it is currently 60). Calculate 60 - 5 = 55. Store 55 in <code>points</code>.
</details>

### Final Thoughts

You have just learned the atom of programming. Almost every complex piece of software—from the video game you play to the banking app you use—is essentially billions of variables being assigned, updated, and read, just like we did here.

For next time, remember the Golden Rule: **Right to Left.**

Class dismissed.