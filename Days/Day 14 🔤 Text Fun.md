### "Playing with Words — Text Fun"

**Goal:** Learn how to manipulate and have fun with text in your programs.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Text is everywhere in programming! Let's learn cool ways to change, analyze, and play with words and sentences.

---

**Step 2 (2 min): Text transformations**  
Type this code and click **Run**:

```python
# Basic text operations
message = "Hello World"

print("Original:", message)
print("Uppercase:", message.upper())
print("Lowercase:", message.lower())
print("Title Case:", message.title())
print("Reversed:", message[::-1])

# Text analysis
print(f"Length: {len(message)} characters")
print(f"Number of words: {len(message.split())}")
print(f"Contains 'World': {'World' in message}")

# Replace text
new_message = message.replace("World", "Python")
print("After replacement:", new_message)
```

🎉 Look at all the ways we can transform text!

The `[::-1]` is a special way to reverse text. `split()` breaks text into words. `in` checks if one text is inside another.

---

**Step 3 (1 min): Word games**  

Let's make some fun word games:

```python
def pig_latin(word):
    """Convert a word to Pig Latin"""
    vowels = "aeiou"
    word = word.lower()
    
    if word[0] in vowels:
        return word + "way"
    else:
        return word[1:] + word[0] + "ay"

def reverse_words(sentence):
    """Reverse each word in a sentence"""
    words = sentence.split()
    reversed_words = [word[::-1] for word in words]
    return " ".join(reversed_words)

# Test the functions
print("Pig Latin:")
print("hello ->", pig_latin("hello"))
print("apple ->", pig_latin("apple"))

print("\nReverse Words:")
print("Hello World ->", reverse_words("Hello World"))

# Interactive word play
user_word = input("\nEnter a word for Pig Latin: ")
print(f"Pig Latin: {pig_latin(user_word)}")
```

---

**Step 4 (1 min): Text art and patterns**  

Create some ASCII art:

```python
def make_border(text, char="*"):
    """Create a decorative border around text"""
    length = len(text)
    border = char * (length + 4)
    
    print(border)
    print(f"{char} {text} {char}")
    print(border)

def pyramid_text(word):
    """Create a text pyramid"""
    for i in range(1, len(word) + 1):
        spaces = " " * (len(word) - i)
        print(spaces + word[:i])

# Try them out
make_border("PYTHON ROCKS!", "=")
print()

pyramid_text("CODING")
print()

# Fun text effects
name = input("Enter your name: ")
print(f"\n🌟 {name.upper()} 🌟")
print("✨" * len(name))
```

---

✅ **Takeaway:**

Text manipulation is powerful and fun! You can transform words, create games, make art, and build interactive experiences with just text operations.

---

[[Day 13 📊 Counting & Tallying|< Day 13]] | [[Day 15 🎨 Simple Projects|Day 15 >]]