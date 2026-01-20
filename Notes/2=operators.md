Welcome back to class. Please settle in.

In our last lecture, we discussed **Variables**. We learned that variables are like boxes in a warehouse—they allow us to store information (data) so we don't lose it.

But simply storing data isn't enough. A warehouse full of wood and nails doesn't give you a table. To build a table, you need to *do* something to that wood. You need to saw it, glue it, and hammer it.

In programming, the wood and nails are your **Variables**.
The saw, glue, and hammer are your **Operators**.

### 1. The Core Concept: Verbs of the Language

If variables are the **Nouns** (the *things*), then Operators are the **Verbs** (the *actions*).

An **Operator** is a special symbol that tells the computer to perform a specific mathematical or logical manipulation. It takes one or two pieces of data (which we call *operands*) and processes them to produce a new result.

We are going to divide these tools into three main toolboxes:
1.  **Arithmetic Operators** (Doing Math)
2.  **Comparison Operators** (Asking Questions)
3.  **Logical Operators** (Making Decisions)

---

### 2. Toolbox 1: Arithmetic Operators (The Calculator)

You are likely already familiar with these from basic mathematics. Python uses them almost exactly the way you learned in grade school.

Imagine you have two variables:
```python
a = 10
b = 3
```

*   **Addition (`+`):** `a + b` results in 13.
*   **Subtraction (`-`):** `a - b` results in 7.
*   **Multiplication (`*`):** `a * b` results in 30. (Note: Computers use an asterisk `*`, not an `x`).

Now, let’s look at **Division**, because this is where computers are very specific.

#### Regular Division (`/`)
This works exactly like a calculator.
```python
result = 10 / 3
# The computer calculates 3.33333...
```

#### Floor Division (`//`)
Sometimes, you don't want a decimal. You want to know how many *whole* times a number fits. This chops off the decimal part completely.
```python
result = 10 // 3
# The computer calculates 3. (It ignores the .3333)
```

#### The Modulo Operator (`%`)
This is the most confusing one for beginners, but it is incredibly useful. The `%` symbol does **not** mean percentage. It means **Remainder**.

Think of this as "Clock Arithmetic." If it is 10:00 and you add 3 hours, it is 1:00 (in a 12-hour cycle). The Modulo operator tells you what remains after you divide perfectly.

```python
remainder = 10 % 3
```
*   **Mental Step:** How many times does 3 go into 10? Three times ($3 \times 3 = 9$).
*   **Mental Step:** What is left over to get to 10? $10 - 9 = 1$.
*   **Result:** 1.

**Real World Use:** If I have a list of user IDs and I want to split them into 2 groups (Group A and Group B), I can check `ID % 2`. If the remainder is 0, they are Even (Group A). If the remainder is 1, they are Odd (Group B).

---

### 3. Toolbox 2: Comparison Operators (The Detective)

Arithmetic operators produce numbers. **Comparison Operators** produce a **True** or **False** answer. They are used to ask the computer questions.

Let's stick with `a = 10` and `b = 3`.

*   **Greater than (`>`):** `a > b` $\rightarrow$ **True**.
*   **Less than (`<`):** `a < b` $\rightarrow$ **False**.

#### The Big Pitfall: Equality (`==`)
This is the most critical distinction in this lecture.

*   `=` (Single Equals) is the **Assignment Operator**. It says "Make this variable equal to this value." It is a command.
*   `==` (Double Equals) is the **Comparison Operator**. It asks "Are these two things equal?" It is a question.

```python
x = 5   # Command: Put 5 in box x.
x == 5  # Question: Is the value in box x equal to 5? (Answer: True)
x == 10 # Question: Is the value in box x equal to 10? (Answer: False)
```

Think of `==` as a detective holding up two evidence bags and asking, "Are these the same?"

---

### 4. Toolbox 3: Logical Operators (The Gatekeeper)

Sometimes we need to ask complex questions. For example: "I will go outside IF it is sunny **AND** I have finished my work."

In Python, we use English words for these: `and`, `or`, `not`.

Assume we have:
```python
is_sunny = True
work_finished = False
```

#### The `and` Operator
Both sides must be True for the result to be True.
*   `is_sunny and work_finished`
*   Computer thinks: "Sunny is True... but work_finished is False. So the whole statement is **False**."

#### The `or` Operator
Only one side needs to be True.
*   `is_sunny or work_finished`
*   Computer thinks: "Sunny is True. I don't even need to check the work. The statement is **True**."

#### The `not` Operator
This flips the value.
*   `not is_sunny` $\rightarrow$ **False**.

---

### 5. How the Computer Thinks: Operator Precedence

Just like in math class (PEMDAS), the computer has a strict order in which it solves these problems.

1.  Parentheses `()`
2.  Arithmetic (Multiplication/Division first, then Addition/Subtraction)
3.  Comparison (`>`, `==`)
4.  Logical (`not`, `and`, `or`)

Let's do a **Dry Run** of a complex line. This is how you should trace code on paper.

```python
x = 5
y = 10
result = (x + 5) == y and y > 2
```

**Step 1: Parentheses**
The computer looks at `(x + 5)`. $x$ is 5. So $5 + 5 = 10$.
*Current state:* `10 == y and y > 2`

**Step 2: Comparison**
The computer looks at `10 == y`. $y$ is 10. Is 10 equal to 10? Yes. That becomes **True**.
The computer looks at `y > 2`. Is 10 greater than 2? Yes. That becomes **True**.
*Current state:* `True and True`

**Step 3: Logic**
`True and True`. Both are true.
*Final Result:* **True**.

---

### 6. Common Beginner Mistakes

**Mistake 1: Confusing `=` and `==`**
```python
# WRONG
if x = 10:
    print("Hello")
```
*   **Why:** You are trying to assign a value inside a question. The computer gets confused. You meant `if x == 10:`.

**Mistake 2: Type Errors**
```python
x = "5"  # This is text (string), not a number
y = 2
print(x + y)
```
*   **Why:** You are asking the computer to add the Letter "5" to the Number 2. It doesn't know if you want "52" or 7. It will crash. You cannot use math operators on mismatched types (usually).

**Mistake 3: Chaining Comparisons Incorrectly**
In math, you might write $5 < x < 10$. Python actually allows this! But many older languages don't. Beginners often try to write it as `5 < x and < 10`, which is a syntax error.

---

### 7. Practice Problems

Take a moment to solve these mentally.

**Problem A: The Remainder**
```python
x = 14
y = 4
result = x % y
print(result)
```
*Question: What prints out?*

<details>
<summary><em>Click to reveal</em></summary>
<strong>Answer: 2</strong><br>
Thinking: How many times does 4 go into 14? 3 times ($4 \times 3 = 12$). What is left over to get to 14? $14 - 12 = 2$.
</details>

<br>

**Problem B: Logic Puzzle**
```python
a = 5
b = 10
check = (a > 2) and (b < 5)
print(check)
```
*Question: Is 'check' True or False?*

<details>
<summary><em>Click to reveal</em></summary>
<strong>Answer: False</strong><br>
Thinking:
1. Is <code>a > 2</code>? Yes (True).
2. Is <code>b < 5</code>? No, 10 is not less than 5 (False).
3. <code>True and False</code> results in <strong>False</strong>.
</details>

### Final Thoughts

You now know how to create storage boxes (Variables) and you have a toolbox full of saws and hammers (Operators) to manipulate what is inside them.

When you look at code, stop reading it like English sentences. Read it like a mathematical sequence. Break it down operator by operator. If you do that, the logic will reveal itself.

Class dismissed.