### "Saving Your Work — Files"

**Goal:** Learn how to save data to files and read it back later.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Sometimes you want your programs to remember things even after they stop running. Files let you save data to your computer and load it back later!

---

**Step 2 (2 min): Writing to files**  
Type this code and click **Run**:

```python
# Writing to a file
def save_to_file():
    # Create and write to a file
    with open("my_notes.txt", "w") as file:
        file.write("Hello, this is my first file!\n")
        file.write("I'm learning to code.\n")
        file.write("Files are pretty cool!\n")
    
    print("✅ File saved as 'my_notes.txt'")

# Reading from a file
def read_from_file():
    try:
        with open("my_notes.txt", "r") as file:
            content = file.read()
            print("📄 File contents:")
            print(content)
    except FileNotFoundError:
        print("❌ File not found! Make sure to save it first.")

# Try both functions
save_to_file()
read_from_file()
```

🎉 You just saved and loaded your first file!

The `with open()` statement safely opens files. `"w"` means write mode, `"r"` means read mode. The `try/except` handles errors if the file doesn't exist.

---

**Step 3 (1 min): Interactive file operations**  

Let's make a simple note-taking program:

```python
def note_taker():
    print("📝 Simple Note Taker")
    
    while True:
        print("\nOptions:")
        print("1. Write a note")
        print("2. Read all notes")
        print("3. Quit")
        
        choice = input("Choose (1-3): ")
        
        if choice == "1":
            note = input("Enter your note: ")
            
            # Append to file (adds to end without erasing)
            with open("notes.txt", "a") as file:
                file.write(f"{note}\n")
            
            print("✅ Note saved!")
        
        elif choice == "2":
            try:
                with open("notes.txt", "r") as file:
                    notes = file.read()
                    if notes:
                        print("\n📄 Your notes:")
                        print(notes)
                    else:
                        print("📄 No notes yet!")
            except FileNotFoundError:
                print("📄 No notes file found. Write a note first!")
        
        elif choice == "3":
            print("👋 Goodbye!")
            break
        
        else:
            print("❌ Invalid choice!")

note_taker()
```

---

**Step 4 (1 min): Working with structured data**  

Save and load more complex data:

```python
import json

def save_high_scores():
    # Dictionary with game scores
    scores = {
        "Alice": 1500,
        "Bob": 1200,
        "Charlie": 1800,
        "Diana": 1350
    }
    
    # Save as JSON (a format for structured data)
    with open("high_scores.json", "w") as file:
        json.dump(scores, file, indent=2)
    
    print("✅ High scores saved!")

def load_high_scores():
    try:
        with open("high_scores.json", "r") as file:
            scores = json.load(file)
        
        print("🏆 High Scores:")
        for name, score in scores.items():
            print(f"  {name}: {score}")
        
        # Find the winner
        winner = max(scores, key=scores.get)
        print(f"\n👑 Top player: {winner} with {scores[winner]} points!")
        
    except FileNotFoundError:
        print("❌ No high scores file found!")

# Test it
save_high_scores()
load_high_scores()

# Add a new score
def add_score():
    name = input("Enter player name: ")
    score = int(input("Enter score: "))
    
    # Load existing scores
    try:
        with open("high_scores.json", "r") as file:
            scores = json.load(file)
    except FileNotFoundError:
        scores = {}
    
    # Add new score
    scores[name] = score
    
    # Save updated scores
    with open("high_scores.json", "w") as file:
        json.dump(scores, file, indent=2)
    
    print(f"✅ Added {name}'s score of {score}!")

add_score()
load_high_scores()
```

---

✅ **Takeaway:**

Files let your programs remember data between runs. Use text files for simple data and JSON for structured data like lists and dictionaries!

---

[[Day 15 🎨 Simple Projects|< Day 15]] | [[Day 17 🕰️ Time & Dates|Day 17 >]]