### "Making Choices with `If`"

**Goal:** Learn that computers can make decisions — _if_ something is true, _then_ do something.  

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Introduce the idea**  

Computers don't think like us, but they _can_ make choices if you tell them how. Today you'll teach the computer to decide what to say.

---

**Step 2 (2 min): Try a simple condition**  
Type this:

```python
answer = input("Do you like ice cream? ")

if answer == "yes":
    print("Yum! Me too!")
```

Run it.  
Type **yes** when it asks.  
Then run it again and type **no** — nothing happens.

The computer _checked_ what you typed. It only talked if your answer was 'yes.'

---

**Step 3 (1 min): Add an 'else' choice**  
Now type:

```python
answer = input("Do you like ice cream? ")

if answer == "yes":
    print("Yum! Me too!")
else:
    print("Oh, more for me then!")
```

Run it and try both answers.

---

**Step 4 (1 min): Reflect**  

What's the word that made the computer _choose_?

That word is `if`. It means: _if this is true, then do that._ Computers can't guess — you have to tell them every possibility.

---

✅ **Takeaway:**

`if` tells the computer to _make a choice._ Logic is just asking questions and reacting to answers.

---

[[Day 3 🔄️ Loops|< Day 3]] | [[Day 5 🪲 Debugging|Day 5 >]]