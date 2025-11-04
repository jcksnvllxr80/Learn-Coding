### "Talking with the User — Input & Output"

**Goal:** Learn how programs can ask questions and get answers from users.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

So far, your programs just talk to you (output). But real programs also listen to you (input). Today you'll make your first interactive program!

---

**Step 2 (2 min): Ask for input**  
Type this code and click **Run**:

```python
name = input("What is your name? ")
print("Nice to meet you,", name)
```

🎉 The program asked you a question and waited for your answer!

The `input()` function shows a message and waits for you to type something. Whatever you type gets stored in the variable.

---

**Step 3 (1 min): Make it more interactive**  

Try this expanded version:

```python
name = input("What is your name? ")
age = input("How old are you? ")
print("Hello", name)
print("Wow, you are", age, "years old!")
```

Now your program has a real conversation with you!

---

**Step 4 (1 min): Reflect**  

Notice these key points:

- Did the program wait for you to type before continuing?
- What happened to the text you typed?

Input lets your programs be interactive. Instead of always doing the same thing, they can respond to what users tell them.

---

✅ **Takeaway:**

Use `input()` to ask users questions and `print()` to show them answers. This makes programs interactive and personal.

---

[[Day 7 🔧 Functions|< Day 7]] | [[Day 9 🏷️ Data Types|Day 9 >]]