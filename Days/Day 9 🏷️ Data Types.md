### "Different Kinds of Information — Data Types"

**Goal:** Learn that computers handle different types of information in different ways.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Just like in real life, there are different types of information: words, numbers, true/false answers. Python treats each type differently, and that's important to understand.

---

**Step 2 (2 min): Explore different types**  
Type this code and click **Run**:

```python
name = "Sarah"          # Text (string)
age = 12               # Number (integer)
height = 4.5           # Decimal number (float)
is_student = True      # True/False (boolean)

print("Name:", name)
print("Age:", age)
print("Height:", height, "feet")
print("Is student:", is_student)
```

🎉 Each variable holds a different type of information!

Text goes in quotes, numbers don't need quotes, and True/False are special words.

---

**Step 3 (1 min): See the difference**  

Try this to see why types matter:

```python
number1 = 5
number2 = 3
text1 = "5"
text2 = "3"

print("Numbers added:", number1 + number2)
print("Text added:", text1 + text2)
```

Numbers get added mathematically (5+3=8), but text gets joined together ("5"+"3"="53")!

---

**Step 4 (1 min): Reflect**  

Notice these key points:

- What happened when you added numbers vs. text?
- Why do you think the computer treats them differently?

Different types of data work in different ways. Understanding this helps you write programs that work correctly.

---

✅ **Takeaway:**

Python has different data types: text (strings), numbers (integers/floats), and True/False (booleans). Each type behaves differently.

---

[[Day 8 💬 Input Output|< Day 8]] | [[Day 10 🧩 Problem Solving|Day 10 >]]