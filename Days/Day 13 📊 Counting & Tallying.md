### "Keeping Score — Counting & Tallying"

**Goal:** Learn how to track and count things in your programs.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Programs often need to count things: how many times something happened, how many items are in a list, or keeping score in games. Let's learn different ways to count and tally!

---

**Step 2 (2 min): Basic counting**  
Type this code and click **Run**:

```python
# Simple counter
count = 0
print("Starting count:", count)

count = count + 1  # Add 1 to count
print("After adding 1:", count)

count += 1  # Shortcut for adding 1
print("After adding 1 more:", count)

count += 5  # Add 5 at once
print("After adding 5:", count)

# Count items in a list
fruits = ["apple", "banana", "orange", "apple", "grape"]
total_fruits = len(fruits)
print(f"Total fruits: {total_fruits}")

# Count specific items
apple_count = fruits.count("apple")
print(f"Number of apples: {apple_count}")
```

🎉 Now you can count anything!

The `+=` operator is a shortcut for adding to a variable. `len()` tells us how many items are in a list. `count()` tells us how many times a specific item appears.

---

**Step 3 (1 min): Advanced tallying**  

Let's count multiple things at once:

```python
# Tally different items
def count_letters(text):
    letter_count = {}  # Dictionary to store counts
    
    for letter in text.lower():
        if letter.isalpha():  # Only count letters
            if letter in letter_count:
                letter_count[letter] += 1
            else:
                letter_count[letter] = 1
    
    return letter_count

# Test it
message = "Hello World"
counts = count_letters(message)

print(f"Letter counts in '{message}':")
for letter, count in counts.items():
    print(f"  {letter}: {count}")
```

---

**Step 4 (1 min): Practical example**  

Here's a vote counter:

```python
def vote_counter():
    votes = {}
    
    print("🗳️ Vote Counter! (type 'done' to finish)")
    
    while True:
        candidate = input("Vote for: ").strip()
        
        if candidate.lower() == 'done':
            break
        
        if candidate in votes:
            votes[candidate] += 1
        else:
            votes[candidate] = 1
        
        print(f"✅ Vote recorded for {candidate}")
    
    print("\n📊 Final Results:")
    for candidate, count in votes.items():
        print(f"  {candidate}: {count} votes")
    
    # Find winner
    if votes:
        winner = max(votes, key=votes.get)
        print(f"\n🏆 Winner: {winner} with {votes[winner]} votes!")

vote_counter()
```

---

✅ **Takeaway:**

Counting and tallying are fundamental programming skills. Use simple counters for basic counting, and dictionaries for tracking multiple categories!

---

[[Day 12 🎯 Simple Games|< Day 12]] | [[Day 14 🔤 Text Fun|Day 14 >]]