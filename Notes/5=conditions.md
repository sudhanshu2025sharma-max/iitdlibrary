Welcome back to class. Please, take your seat.

In our previous lectures, we built a foundation. We learned to store data in **Variables**, manipulate it with **Operators**, and categorize it with **Data Types**.

Up until this moment, every program we have written has been a straight line. The computer starts at line 1, executes line 2, then line 3, and so on, until it hits the end. It is like a train on a single track; it has no choice but to go forward.

But the real world is not a straight line. The real world is full of choices.
*   *If* it is raining, take an umbrella. *Otherwise*, leave it at home.
*   *If* the password is correct, log in. *Otherwise*, show an error.

To make our programs useful, we need to give them the power of **decision-making**. We need to install switches on that train track. In Computer Science, we call this concept **Conditionals**, or **Control Flow**.

---

### 1. The Mental Model: The Gatekeeper

Imagine you are trying to enter a secure building. There is a security guard standing at the door.
The guard asks you a specific question.
*   **The Question:** "Do you have an ID badge?"

This question can only be answered with a **Yes** (True) or a **No** (False).

*   **If Yes (True):** The guard opens the door, and you walk inside to do your business.
*   **If No (False):** The guard keeps the door locked. You are denied entry and must skip whatever is inside that building.

In Python, the `if` statement is that security guard.

---

### 2. The Syntax: Indentation as Structure

Before we write code, we must discuss **Indentation**.

In many languages, we use brackets `{ }` to group things. Python is different. Python uses **white space** (tabs or spaces) to show grouping.

Think of an indented block of code as a "sub-paragraph." It belongs to the line above it.

```python
if condition:
    # This code is "inside" the If statement
    # It only runs if the condition is True
    
# This code is back on the main track
# It runs no matter what
```

**The Colon (`:`):** Do not forget the colon at the end of the `if` line. The colon basically says to the computer: *"Okay, here comes the block of code I want you to control."*

---

### 3. Level 1: The Simple `if` Statement

Let's look at the simplest possible case. We want to check if a user is old enough to vote.

```python
age = 20

if age >= 18:
    print("You are eligible to vote.")

print("Program finished.")
```

**The Computer's Mental Dry-Run:**
1.  **Line 1:** `age` is assigned `20`.
2.  **Line 3:** The `if` keyword acts as the Gatekeeper. It asks the question: *Is `age` (20) greater than or equal to 18?*
3.  **Evaluation:** The answer is **True**.
4.  **Action:** Because it is True, the computer enters the indented block.
5.  **Line 4:** It prints "You are eligible to vote."
6.  **Line 6:** It continues to the end.

**What if `age` was 10?**
1.  **Evaluation:** Is 10 >= 18? **False**.
2.  **Action:** The computer *skips* the indented line (Line 4) entirely. It jumps straight to Line 6. The text "You are eligible to vote" is never touched.

---

### 4. Level 2: The `else` (The Alternative Path)

In the previous example, if the person was too young, the program just did nothing. That is rarely what we want. Usually, we want two distinct paths: Path A for Success, Path B for Failure.

We use the keyword `else`. Think of `else` as "Otherwise."

```python
age = 15

if age >= 18:
    print("Welcome, voter.")
else:
    print("Sorry, you are too young.")

print("Next customer please.")
```

**Key Concept:** These two blocks are **Mutually Exclusive**. The computer will execute the `if` block OR the `else` block. It will never, ever do both. It is a fork in the road; you cannot go left and right at the same time.

---

### 5. Level 3: The `elif` (Multiple Choice)

Life isn't always binary (Yes/No). Sometimes we have three or four options.
Imagine a traffic light: Green, Yellow, Red.

In Python, we use `elif`. This is short for "Else If."

```python
light_color = "Yellow"

if light_color == "Green":
    print("Go")
elif light_color == "Yellow":
    print("Slow down")
else:
    print("Stop")
```

**How the Computer Thinks (The Ladder Logic):**
The computer checks these conditions strictly from **Top to Bottom**.

1.  **Check 1:** Is it Green? (False). *Skip the first block.*
2.  **Check 2:** Okay, is it Yellow? (True). *Enter this block!*
3.  **Action:** Print "Slow down."
4.  **Escape:** Because it found a match, it **ignores the rest of the chain**. It does not check the `else`. It jumps to the very end.

**The "Catch-All" `else`:**
The final `else` is optional, but it acts as a safety net. If none of the conditions above are met, the `else` catches everything that is left over.

---

### 6. Common Beginner Mistakes

**Mistake 1: The Assignment Trap**
We discussed this in the Operators lecture, but it happens constantly with Conditions.
```python
# WRONG
if x = 10:
    print("x is 10")
```
*   **Why:** `=` creates a variable. `==` compares variables. You cannot create a variable inside the Gatekeeper's question. You must use `if x == 10:`.

**Mistake 2: Indentation Errors**
```python
if x > 5:
print("Big Number") # Error!
```
*   **Why:** The computer expects the code inside the `if` to be pushed to the right. If it isn't, the computer thinks the `if` statement is empty and gets confused.

**Mistake 3: Logic Order (The Filter Problem)**
Order matters immensely in an `if/elif` chain. Look at this logical error:

```python
score = 95

if score > 50:
    print("You passed!")
elif score > 90:
    print("You got an A!")
```
*   **The Issue:** A score of 95 is greater than 50. The computer sees the first `if` is True, prints "You passed!", and **stops checking**. It never reaches the "You got an A!" line.
*   **The Fix:** Always check the most specific (hardest) condition first. Check for > 90 before you check for > 50.

---

### 7. Practice Problems

Let's trace these mentally to ensure you understand the flow.

**Problem A: The Weather App**
```python
temp = 30
is_raining = True

if temp > 20:
    print("It is warm.")
    if is_raining:
        print("Bring an umbrella.")
else:
    print("It is cold.")
```
*Question: What exactly prints out to the screen?*

<details>
<summary><em>Click to reveal the professor's thinking</em></summary>
<strong>Answer:</strong>
It is warm.<br>
Bring an umbrella.
<br><br>
<strong>Reasoning:</strong>
1. First Check: Is <code>temp > 20</code>? Yes (30 > 20). Enter the first block.
2. Print "It is warm."
3. Inside this block, there is a <strong>Nested If</strong> (an If inside an If).
4. Second Check: Is <code>is_raining</code> True? Yes.
5. Print "Bring an umbrella."
</details>

<br>

**Problem B: The Multiple If Trap**
```python
x = 10

if x > 5:
    print("A")
if x > 8:
    print("B")
else:
    print("C")
```
*Question: Does this print just "A", or "A" and "B"?*

<details>
<summary><em>Click to reveal the professor's thinking</em></summary>
<strong>Answer:</strong>
A<br>
B
<br><br>
<strong>Reasoning:</strong>
Notice there is no <code>elif</code>. These are two completely separate chains.
1. First If: Is 10 > 5? Yes. Print "A".
2. The computer continues down. It hits a <strong>new</strong> If statement.
3. Second If: Is 10 > 8? Yes. Print "B".
4. The <code>else</code> belongs to the second If, so it is skipped.
<br>
<em>If we had used <code>elif</code> for the second check, it would have only printed "A".</em>
</details>

### Final Thoughts

Conditions are the logic of the machine. They allow the computer to be dynamic rather than static.

When you write an `if` statement, you are essentially drawing a map. You are telling the computer: "When you get to this intersection, look at the sign. If the sign says X, go left. If it says Y, go right."

Mastering this flow is the first step toward algorithmic thinking.

Class dismissed.

number =  int(input("What is your number? \n"))
even = number % 2


if even == 0:
    print("even")
    name = str(input("what is your name? "))
    
    if name == "sudhanshu":
        print("hii")        
    else: 
        print("who?")

else:
    print("odd")