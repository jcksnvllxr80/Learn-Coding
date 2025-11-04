### "Password Generator & Quiz Game — Mini Projects"

**Goal:** Build two complete mini-projects that combine multiple programming concepts.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Let's build two useful programs: a password generator for security and a quiz game for fun. These projects will use everything you've learned!

---

**Step 2 (2 min): Password Generator**  
Type this code and click **Run**:

```python
import random
import string

def generate_password(length=12, include_symbols=True):
    """Generate a secure random password"""
    
    # Character sets
    lowercase = string.ascii_lowercase  # a-z
    uppercase = string.ascii_uppercase  # A-Z
    digits = string.digits              # 0-9
    symbols = "!@#$%^&*()_+-=[]{}|;:,.<>?"
    
    # Build character pool
    characters = lowercase + uppercase + digits
    if include_symbols:
        characters += symbols
    
    # Ensure password has at least one of each type
    password = []
    password.append(random.choice(lowercase))
    password.append(random.choice(uppercase))
    password.append(random.choice(digits))
    
    if include_symbols:
        password.append(random.choice(symbols))
    
    # Fill remaining length with random characters
    for _ in range(length - len(password)):
        password.append(random.choice(characters))
    
    # Shuffle the password
    random.shuffle(password)
    
    return ''.join(password)

def password_generator():
    """Interactive password generator"""
    print("🔐 Secure Password Generator")
    
    while True:
        print("\nOptions:")
        print("1. Generate password")
        print("2. Generate multiple passwords")
        print("3. Custom password settings")
        print("4. Quit")
        
        choice = input("Choose (1-4): ")
        
        if choice == "1":
            password = generate_password()
            print(f"🔑 Your password: {password}")
        
        elif choice == "2":
            count = int(input("How many passwords? "))
            print(f"\n🔑 {count} Random Passwords:")
            for i in range(count):
                password = generate_password()
                print(f"  {i+1}. {password}")
        
        elif choice == "3":
            length = int(input("Password length (8-50): "))
            length = max(8, min(50, length))  # Keep between 8-50
            
            symbols_choice = input("Include symbols? (y/n): ").lower()
            include_symbols = symbols_choice == 'y'
            
            password = generate_password(length, include_symbols)
            print(f"🔑 Your custom password: {password}")
        
        elif choice == "4":
            print("🔐 Stay secure!")
            break
        
        else:
            print("❌ Invalid choice!")

password_generator()
```

🎉 You built a professional-grade password generator!

---

**Step 3 (1 min): Quiz Game**  

Now let's build an interactive quiz:

```python
import random

def quiz_game():
    """Interactive quiz game with multiple categories"""
    
    # Quiz questions organized by category
    quizzes = {
        "python": {
            "name": "Python Programming",
            "questions": [
                {"q": "What keyword is used to define a function in Python?", "a": "def"},
                {"q": "What symbol starts a comment in Python?", "a": "#"},
                {"q": "What function is used to get user input?", "a": "input"},
                {"q": "What data type is [1, 2, 3]?", "a": "list"},
                {"q": "What keyword is used for loops that repeat a specific number of times?", "a": "for"}
            ]
        },
        "general": {
            "name": "General Knowledge",
            "questions": [
                {"q": "What is the capital of France?", "a": "paris"},
                {"q": "How many days are in a leap year?", "a": "366"},
                {"q": "What planet is known as the Red Planet?", "a": "mars"},
                {"q": "What is 7 x 8?", "a": "56"},
                {"q": "What gas do plants absorb from the atmosphere?", "a": "carbon dioxide"}
            ]
        },
        "fun": {
            "name": "Fun Facts",
            "questions": [
                {"q": "What animal is known as the 'King of the Jungle'?", "a": "lion"},
                {"q": "How many sides does a hexagon have?", "a": "6"},
                {"q": "What is the fastest land animal?", "a": "cheetah"},
                {"q": "What is the largest ocean on Earth?", "a": "pacific"},
                {"q": "What fruit is known for keeping doctors away?", "a": "apple"}
            ]
        }
    }
    
    print("🧠 Quiz Game!")
    print("Test your knowledge!\n")
    
    # Choose category
    print("Categories:")
    for key, quiz in quizzes.items():
        print(f"  {key}: {quiz['name']}")
    
    category = input("\nChoose a category: ").lower()
    
    if category not in quizzes:
        print("❌ Invalid category!")
        return
    
    # Start quiz
    selected_quiz = quizzes[category]
    questions = selected_quiz["questions"].copy()
    random.shuffle(questions)  # Randomize order
    
    score = 0
    total_questions = len(questions)
    
    print(f"\n🎯 Starting {selected_quiz['name']} Quiz!")
    print(f"Answer {total_questions} questions. Good luck!\n")
    
    for i, question in enumerate(questions, 1):
        print(f"Question {i}/{total_questions}:")
        print(question["q"])
        
        user_answer = input("Your answer: ").lower().strip()
        correct_answer = question["a"].lower()
        
        if user_answer == correct_answer:
            print("✅ Correct!\n")
            score += 1
        else:
            print(f"❌ Wrong! The answer was: {question['a']}\n")
    
    # Final score
    percentage = (score / total_questions) * 100
    
    print("🏆 Quiz Complete!")
    print(f"Final Score: {score}/{total_questions} ({percentage:.1f}%)")
    
    if percentage >= 80:
        print("🌟 Excellent work!")
    elif percentage >= 60:
        print("👍 Good job!")
    elif percentage >= 40:
        print("📚 Keep studying!")
    else:
        print("💪 Practice makes perfect!")

quiz_game()
```

---

**Step 4 (1 min): Combined launcher**  

Create a program that lets you choose which project to run:

```python
def project_launcher():
    """Launch different mini projects"""
    
    print("🎪 Mini Projects Launcher!")
    print("Choose a project to run:\n")
    
    while True:
        print("Available Projects:")
        print("1. 🔐 Password Generator")
        print("2. 🧠 Quiz Game")
        print("3. 🎲 Random Project")
        print("4. 🚪 Exit")
        
        choice = input("\nChoose (1-4): ")
        
        if choice == "1":
            print("\n" + "="*50)
            password_generator()
            print("="*50 + "\n")
        
        elif choice == "2":
            print("\n" + "="*50)
            quiz_game()
            print("="*50 + "\n")
        
        elif choice == "3":
            import random
            projects = [password_generator, quiz_game]
            random_project = random.choice(projects)
            print(f"\n🎲 Random project selected!")
            print("="*50)
            random_project()
            print("="*50 + "\n")
        
        elif choice == "4":
            print("👋 Thanks for trying the mini projects!")
            break
        
        else:
            print("❌ Invalid choice!")

project_launcher()
```

---

✅ **Takeaway:**

Mini projects are great for practicing! They combine multiple concepts and create useful, real-world applications. Keep building projects to improve your skills!

---

[[Day 18 🌐 Simple Web|< Day 18]] | [[Day 20 🔄 Algorithms|Day 20 >]]