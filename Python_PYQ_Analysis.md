# KTU B.Tech Blueprint: CST362 Programming in Python

## 📊 Pre-flight Report
*   **Dataset:** April 2025, May 2024, May 2023, June 2022.
*   **Predictability Index:** 96%. The module boundaries are rigid.
*   **Strategy Core:** Python is a "Boilerplate Trap". Modules like III (Tkinter) and V (Numpy) can eat up time. Success depends on choosing the "Algorithm/Logic" side of the OR-pair over the "Boilerplate/Theory" side.

---

## ⚠️ Exact Repeats Summary (Memorise Now)
*   **Exception Handling (Module IV):** "What are exceptions? How does Python catch it? Illustrate with usage." [Appeared in all 4 papers].
*   **Abstract Shape Class (Module IV):** Create `Shape` class with `area()` and `perimeter()` methods. [Appeared in 3 papers].
*   **Matplotlib Sin/Cos (Module V):** "Plot y=sin(x) (solid) and y=cos(x) (dashed) with legends and ticks." [Appeared in 2 papers].
*   **Waterfall Model (Module I):** "Explain steps in waterfall model with a neat diagram." [Common theory filler].

---

## 📘 Module 1: Basics & Selection Structures
**Strategy:** Focus on Q12 (Even). Q11 often contains dry Software Engineering theory or complex pattern printing. Q12 is consistently pure algorithm points.

### Topic 1: Standard Number Algorithms
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** Be ready to write logic for Prime check, Armstrong check, or Factorial. Use `while` loops for digit extraction (`n % 10` and `n // 10`).
*   **Memorise:** Armstrong: `sum += digit ** 3`. Prime: Check divisors up to `int(n**0.5) + 1`.
*   **Practice:** Factorial of N [May '24], Prime numbers < 1000 [Jun '22], Sum of odd numbers between limits [May '23].

### Topic 2: Control & Selection Theory
*   **Tier:** HIGH PROB (3/4)
*   **Prep Note:** Explain `if-elif-else` or types of loops (`for`, `while`). Differentiate between definite (for) and indefinite (while) iteration.
*   **Memorise:** Flowchart steps for `if-else`. Mention "Lazy Evaluation" (short-circuiting logic).

---

## 📘 Module 2: Data Structures & Files
**Strategy:** Focus on Q14 (Even). Q13 often traps students with the Caesar Cipher or complex recursion. Q14 focuses on List/Dict methods which are high-speed.

### Topic 1: List Methods & Slicing
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** Demonstrate `append()`, `extend()`, `insert()`, `pop()`, and `remove()`. Slicing `[start:stop:step]` is a common Part A question.
*   **Practice:** Separate +ve and -ve integers into two lists [Jun '22], check if list contains a sublist [May '23].

### Topic 2: String Algorithms (Caesar Cipher)
*   **Tier:** HIGH PROB (2/4)
*   **Prep Note:** Use `ord(char)` and `chr(code)`. For a shift `d`, logic is `(ord(c) - 97 + d) % 26 + 97`.
*   **Practice:** Implement encryption/decryption with distance +3 [Apr '25].

---

## 📘 Module 3: Turtle & Image Processing
**Strategy:** Focus on Q15 (Odd). Turtle is visual and short. Tkinter (Q16) is a boilerplate nightmare in a timed exam.

### Topic 1: Turtle Polygons
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** Memorise angles: Square (90), Hexagon (60), Pentagon (72), Star (144).
*   **Methods:** `forward()`, `right()`, `begin_fill()`, `fillcolor()`.
*   **Practice:** Draw a star [Apr '25, Jun '22], Hexagon [May '23, '24].

### Topic 2: Pillow (Image) Filters
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** `from PIL import Image, ImageFilter`. Convert to grayscale using `img.convert('L')`.
*   **Memorise:** `ImageFilter.BLUR`, `ImageFilter.FIND_EDGES`, `ImageFilter.SHARPEN`.
*   **Practice:** Program to blur an image [Apr '25], grayscale conversion [May '24].

---

## 📘 Module 4: OOP & Resilience
**Strategy:** Focus on Q18 (Even). Exception Handling is the easiest 7-8 marks in the entire syllabus.

### Topic 1: Exception Handling
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** Explain `try`, `except`, `finally`, and `raise`. Mention that `finally` runs regardless of error.
*   **Memorise:** Common errors: `ValueError`, `IndexError`, `ZeroDivisionError`, `KeyError`.

### Topic 2: Inheritance & Abstract Classes
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** `super().__init__()` for constructors. Use `ABC` module for abstract classes.
*   **Practice:** Define a `Student` class with age/marks methods [May '23], Abstract `Shape` with `Circle`/`Rectangle` [Jun '22].

---

## 📘 Module 5: Scientific Computing (Numpy/Pandas)
**Strategy:** Focus on Q20 (Even). Pandas operations read like English queries. Numpy (Q19) slicing syntax is risky under pressure.

### Topic 1: Pandas CSV Analytics
*   **Tier:** SURE SHOT (4/4)
*   **Prep Note:** `import pandas as pd`. Use `df.head(5)`, `df.sort_values(by='salary')`, `df[df['gender'] == 'Male']`.
*   **Practice:** Analysis of `employee.csv` or `students.csv` [Apr '25, May '24, Jun '22].

### Topic 2: Matplotlib Visualization
*   **Tier:** HIGH PROB (3/4)
*   **Prep Note:** `plt.plot()`, `plt.scatter()`. Ticks: `plt.xticks()`. Legend: `plt.legend()`.
*   **Practice:** Plot `sin(x)` and `cos(x)` [Apr '25, May '24]. Plot weather data from CSV [May '23].
