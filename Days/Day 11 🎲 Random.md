### "Making the Computer Surprise You — Random"

**Goal:** Learn how computers can generate random numbers and make unpredictable choices.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Sometimes we want our programs to be unpredictable! Random numbers let computers make surprising choices, just like rolling dice or flipping coins.

---

**Step 2 (2 min): Generate random numbers**  
Type this code and click **Run**:

```python
import random

print("Let me pick a random number between 1 and 10...")
random_number = random.randint(1, 10)
print("I picked:", random_number)

print("\nLet me flip a coin...")
coin = random.choice(["Heads", "Tails"])
print("Result:", coin)
```

🎉 Run it several times and watch the computer surprise you with different results!

The `import random` line gives us access to random functions. `randint(1, 10)` picks a random whole number between 1 and 10. `choice()` randomly picks one item from a list.

---

**Step 3 (1 min): Make it interactive**  

Try this fun program:

```python
import random

name = input("What's your name? ")
colors = ["red", "blue", "green", "yellow", "purple"]
lucky_color = random.choice(colors)

print(f"Hello {name}! Your lucky color today is {lucky_color}!")
```

---

**Step 4 (1 min): Reflect**  

Random numbers are everywhere in programming:
- Games (dice rolls, card shuffling)
- Passwords (random characters)
- Art (random colors and shapes)
- Simulations (modeling real-world randomness)

---

✅ **Takeaway:**

Random numbers make programs more interesting and unpredictable. They're essential for games, security, and simulating real-world scenarios!

---

[[Day 10 🧩 Problem Solving|< Day 10]] | [[Day 12 🎯 Simple Games|Day 12 >]]