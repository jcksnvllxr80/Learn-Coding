### "Putting It All Together — Problem Solving"

**Goal:** Learn to break down problems into smaller steps using everything you've learned.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

You've learned commands, sequencing, loops, logic, debugging, variables, functions, input/output, and data types. Now let's use them all together to solve a real problem!

---

**Step 2 (2 min): Build a complete program**  
Let's make a simple guessing game. Type this code and click **Run**:

```python
def guessing_game():
    secret_number = 7
    print("I'm thinking of a number between 1 and 10!")
    
    guess = input("What's your guess? ")
    guess = int(guess)  # Convert text to number
    
    if guess == secret_number:
        print("Wow! You got it right!")
    else:
        print("Not quite! The number was", secret_number)

guessing_game()
```

🎉 You just built a complete interactive program!

This uses variables (secret_number, guess), functions (guessing_game), input/output, data types (converting text to number), and logic (if/else).

---

**Step 3 (1 min): Enhance it**  

Try adding a loop to let them guess multiple times:

```python
def guessing_game():
    secret_number = 7
    print("I'm thinking of a number between 1 and 10!")
    
    for attempt in range(3):
        guess = input("What's your guess? ")
        guess = int(guess)
        
        if guess == secret_number:
            print("Wow! You got it right!")
            break
        else:
            print("Not quite! Try again.")
    
    print("The number was", secret_number)

guessing_game()
```

---

**Step 4 (1 min): Reflect**  

Notice how you combined everything:

- Functions to organize code
- Variables to store information  
- Input/output to interact with users
- Logic to make decisions
- Loops for repetition
- Data types to handle different information

This is how real programming works — combining simple concepts to solve complex problems!

---

✅ **Takeaway:**

Programming is about breaking big problems into small steps and combining basic concepts. You now have the foundation to build amazing things!

---

[[Day 9 🏷️ Data Types|< Day 9]] | [[Day 11 🎲 Random|Day 11 >]]