### "What Time Is It? — Time & Dates"

**Goal:** Learn how to work with time and dates in your programs.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

Programs often need to know what time it is, calculate how much time has passed, or work with dates. Let's learn how to handle time in code!

---

**Step 2 (2 min): Getting current time**  
Type this code and click **Run**:

```python
import datetime

# Get current date and time
now = datetime.datetime.now()
print("Current date and time:", now)

# Get just the date
today = datetime.date.today()
print("Today's date:", today)

# Format time nicely
formatted_time = now.strftime("%Y-%m-%d %H:%M:%S")
print("Formatted time:", formatted_time)

# Different formats
print("Just the time:", now.strftime("%H:%M:%S"))
print("Month/Day/Year:", now.strftime("%m/%d/%Y"))
print("Day of week:", now.strftime("%A"))
print("Month name:", now.strftime("%B"))
```

🎉 Now you can get the current time in any format!

The `datetime` module handles all time operations. `strftime()` formats time into readable strings using special codes like `%Y` for year, `%m` for month, etc.

---

**Step 3 (1 min): Time calculations**  

Let's do some time math:

```python
import datetime

# Calculate your age in days
def calculate_age_in_days():
    birth_year = int(input("What year were you born? "))
    birth_month = int(input("What month (1-12)? "))
    birth_day = int(input("What day? "))
    
    # Create birthday date
    birthday = datetime.date(birth_year, birth_month, birth_day)
    today = datetime.date.today()
    
    # Calculate difference
    age_in_days = (today - birthday).days
    
    print(f"You are {age_in_days} days old!")
    print(f"That's {age_in_days // 365} years and {age_in_days % 365} days!")

calculate_age_in_days()

# Time until next birthday
def days_until_birthday():
    today = datetime.date.today()
    
    birth_month = int(input("Birth month (1-12): "))
    birth_day = int(input("Birth day: "))
    
    # This year's birthday
    this_year_birthday = datetime.date(today.year, birth_month, birth_day)
    
    # If birthday already passed this year, use next year
    if this_year_birthday < today:
        next_birthday = datetime.date(today.year + 1, birth_month, birth_day)
    else:
        next_birthday = this_year_birthday
    
    days_left = (next_birthday - today).days
    print(f"Days until your birthday: {days_left}")

days_until_birthday()
```

---

**Step 4 (1 min): Time-based programs**  

Create programs that respond to time:

```python
import datetime
import time

def time_greeting():
    """Give different greetings based on time of day"""
    now = datetime.datetime.now()
    hour = now.hour
    
    if 5 <= hour < 12:
        greeting = "Good morning"
    elif 12 <= hour < 17:
        greeting = "Good afternoon"
    elif 17 <= hour < 21:
        greeting = "Good evening"
    else:
        greeting = "Good night"
    
    print(f"{greeting}! It's {now.strftime('%I:%M %p')}")

time_greeting()

def countdown_timer():
    """Simple countdown timer"""
    seconds = int(input("Countdown from how many seconds? "))
    
    print("Starting countdown...")
    
    for i in range(seconds, 0, -1):
        print(f"{i}...")
        time.sleep(1)  # Wait 1 second
    
    print("🎉 Time's up!")

# Uncomment to try the timer (it takes real time!)
# countdown_timer()

def event_tracker():
    """Track when events happen"""
    events = []
    
    while True:
        print("\n1. Add event")
        print("2. Show all events")
        print("3. Quit")
        
        choice = input("Choose: ")
        
        if choice == "1":
            event = input("What happened? ")
            timestamp = datetime.datetime.now()
            events.append((event, timestamp))
            print("✅ Event recorded!")
        
        elif choice == "2":
            if events:
                print("\n📅 Event History:")
                for event, timestamp in events:
                    formatted_time = timestamp.strftime("%m/%d/%Y %I:%M:%S %p")
                    print(f"  {formatted_time}: {event}")
            else:
                print("No events recorded yet!")
        
        elif choice == "3":
            break

event_tracker()
```

---

✅ **Takeaway:**

Time and dates are essential for many programs. You can get current time, format it nicely, do calculations, and create time-aware applications!

---

[[Day 16 📁 Files|< Day 16]] | [[Day 18 🌐 Simple Web|Day 18 >]]