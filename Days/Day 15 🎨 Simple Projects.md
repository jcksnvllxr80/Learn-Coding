### "Mad Libs Generator — Simple Projects"

**Goal:** Build a complete project that combines text manipulation, user input, and creative output.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Mad Libs are stories with missing words that you fill in to create funny results! This project combines everything you've learned: input, text manipulation, and creative programming.

---

**Step 2 (2 min): Build a basic Mad Libs**  
Type this code and click **Run**:

```python
def simple_mad_libs():
    print("🎭 Welcome to Mad Libs Generator!")
    print("I'll ask for some words, then create a funny story!\n")
    
    # Collect words
    adjective1 = input("Give me an adjective (describing word): ")
    noun1 = input("Give me a noun (person, place, or thing): ")
    verb1 = input("Give me a verb (action word): ")
    adjective2 = input("Give me another adjective: ")
    noun2 = input("Give me another noun: ")
    
    # Create the story
    story = f"""
    🌟 Your Mad Libs Story! 🌟
    
    Once upon a time, there was a {adjective1} {noun1} who loved to {verb1}.
    Every day, they would {verb1} around the {adjective2} {noun2}.
    All the other {noun1}s thought this was very {adjective2}!
    The end.
    """
    
    print(story)

simple_mad_libs()
```

🎉 You just created a story generator!

---

**Step 3 (1 min): Add multiple story templates**  

Let's make it more interesting with different stories:

```python
import random

def advanced_mad_libs():
    print("🎭 Advanced Mad Libs Generator!")
    print("Choose your adventure!\n")
    
    # Story templates
    stories = {
        "adventure": {
            "prompts": ["adjective", "noun", "verb", "place", "animal"],
            "template": "The {adjective} explorer decided to {verb} through the {place}. Suddenly, a wild {animal} appeared! It was the most {adjective} {noun} they had ever seen!"
        },
        "school": {
            "prompts": ["adjective", "subject", "verb", "food", "number"],
            "template": "At {adjective} school, students love to study {subject}. During lunch, they {verb} while eating {food}. The teacher gave them {number} homework problems!"
        },
        "space": {
            "prompts": ["color", "planet", "verb", "alien name", "adjective"],
            "template": "Captain {alien name} flew their {color} spaceship to {planet}. The aliens there love to {verb} all day! It was a very {adjective} adventure!"
        }
    }
    
    # Let user choose story type
    print("Story types:")
    for story_type in stories.keys():
        print(f"  - {story_type}")
    
    choice = input("\nWhich story type? ").lower()
    
    if choice in stories:
        story_data = stories[choice]
        words = {}
        
        # Collect words
        for prompt in story_data["prompts"]:
            words[prompt] = input(f"Give me a {prompt}: ")
        
        # Generate story
        final_story = story_data["template"].format(**words)
        
        print(f"\n🌟 Your {choice.title()} Story! 🌟")
        print(final_story)
    else:
        print("That's not a valid story type!")

advanced_mad_libs()
```

---

**Step 4 (1 min): Make it reusable**  

Add the ability to play multiple times:

```python
import random

def mad_libs_game():
    stories = [
        {
            "prompts": ["silly adjective", "animal", "verb ending in -ing", "place", "food"],
            "template": "I saw a {silly adjective} {animal} {verb ending in -ing} at the {place} while eating {food}!"
        },
        {
            "prompts": ["color", "number", "noun", "verb", "adjective"],
            "template": "There were {number} {color} {noun}s who loved to {verb}. Everyone said they were very {adjective}!"
        },
        {
            "prompts": ["name", "adjective", "hobby", "place", "emotion"],
            "template": "My friend {name} is very {adjective}. They love {hobby} at the {place}. It makes them feel {emotion}!"
        }
    ]
    
    print("🎭 Mad Libs Game! 🎭")
    
    while True:
        # Pick random story
        story = random.choice(stories)
        words = {}
        
        print("\nLet's create a story!")
        for prompt in story["prompts"]:
            words[prompt] = input(f"Give me a {prompt}: ")
        
        # Generate and show story
        final_story = story["template"].format(**words)
        print(f"\n✨ {final_story} ✨\n")
        
        # Ask to play again
        play_again = input("Want to create another story? (yes/no): ").lower()
        if play_again != "yes":
            print("Thanks for playing! 🎉")
            break

mad_libs_game()
```

---

✅ **Takeaway:**

Mad Libs combines user input, text formatting, randomness, and creativity. This is what makes programming fun - building interactive experiences that surprise and delight!

---

[[Day 14 🔤 Text Fun|< Day 14]] | [[Day 16 📁 Files|Day 16 >]]