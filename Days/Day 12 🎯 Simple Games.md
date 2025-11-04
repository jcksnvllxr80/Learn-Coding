### "Rock, Paper, Scissors — Simple Games"

**Goal:** Build your first complete game using everything you've learned so far.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Games are perfect for practicing programming! They combine user input, random choices, logic, and output. Let's build the classic Rock, Paper, Scissors game.

---

**Step 2 (2 min): Build the basic game**  
Type this code and click **Run**:

```python
import random

def rock_paper_scissors():
    print("Let's play Rock, Paper, Scissors!")
    
    # Get player choice
    player_choice = input("Choose rock, paper, or scissors: ").lower()
    
    # Computer makes random choice
    choices = ["rock", "paper", "scissors"]
    computer_choice = random.choice(choices)
    
    print(f"You chose: {player_choice}")
    print(f"Computer chose: {computer_choice}")
    
    # Determine winner
    if player_choice == computer_choice:
        print("It's a tie!")
    elif (player_choice == "rock" and computer_choice == "scissors") or \
         (player_choice == "paper" and computer_choice == "rock") or \
         (player_choice == "scissors" and computer_choice == "paper"):
        print("You win!")
    else:
        print("Computer wins!")

rock_paper_scissors()
```

🎉 You just built a complete game!

---

**Step 3 (1 min): Add multiple rounds**  

Let's make it even better with multiple rounds:

```python
import random

def play_round():
    choices = ["rock", "paper", "scissors"]
    
    player_choice = input("Choose rock, paper, or scissors: ").lower()
    computer_choice = random.choice(choices)
    
    print(f"You: {player_choice} | Computer: {computer_choice}")
    
    if player_choice == computer_choice:
        return "tie"
    elif (player_choice == "rock" and computer_choice == "scissors") or \
         (player_choice == "paper" and computer_choice == "rock") or \
         (player_choice == "scissors" and computer_choice == "paper"):
        return "player"
    else:
        return "computer"

def rock_paper_scissors_game():
    print("🎮 Rock, Paper, Scissors Game!")
    print("Best of 3 rounds!\n")
    
    player_wins = 0
    computer_wins = 0
    
    for round_num in range(1, 4):
        print(f"Round {round_num}:")
        result = play_round()
        
        if result == "player":
            print("You win this round! 🎉")
            player_wins += 1
        elif result == "computer":
            print("Computer wins this round! 🤖")
            computer_wins += 1
        else:
            print("This round is a tie! 🤝")
        
        print(f"Score: You {player_wins} - {computer_wins} Computer\n")
    
    # Final result
    if player_wins > computer_wins:
        print("🏆 You win the game!")
    elif computer_wins > player_wins:
        print("🤖 Computer wins the game!")
    else:
        print("🤝 The game is a tie!")

rock_paper_scissors_game()
```

---

**Step 4 (1 min): Reflect**  

Notice how this game uses:
- **Functions** to organize code
- **Random** for computer choices
- **Input/Output** for interaction
- **Logic** to determine winners
- **Loops** for multiple rounds
- **Variables** to keep score

---

✅ **Takeaway:**

Games are excellent programming practice because they combine many concepts in fun, interactive ways!

---

[[Day 11 🎲 Random|< Day 11]] | [[Day 13 📊 Counting & Tallying|Day 13 >]]