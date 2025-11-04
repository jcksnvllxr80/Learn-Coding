### "Talking to the Internet — Simple Web"

**Goal:** Learn how to get information from the internet in your programs.

---

#### 🕐 **Total time: ≈ 5 minutes**

**Step 1 (1 min): Set the scene**  

The internet is full of information! Your programs can fetch data from websites, get weather updates, download images, and much more. Let's learn the basics!

---

**Step 2 (2 min): Making web requests**  
Type this code and click **Run**:

```python
import requests
import json

# Simple web request
def get_random_fact():
    """Get a random fun fact from the internet"""
    try:
        # Make a request to an API (Application Programming Interface)
        response = requests.get("https://uselessfacts.jsph.pl/random.json?language=en")
        
        if response.status_code == 200:  # Success!
            data = response.json()  # Convert response to Python dictionary
            fact = data['text']
            print("🤓 Random Fact:")
            print(fact)
        else:
            print("❌ Couldn't get a fact right now")
    
    except requests.exceptions.RequestException:
        print("❌ No internet connection or API is down")

get_random_fact()

# Get multiple facts
def get_multiple_facts():
    print("🎲 Getting 3 random facts...\n")
    
    for i in range(3):
        print(f"Fact #{i+1}:")
        get_random_fact()
        print()

get_multiple_facts()
```

🎉 Your program just talked to the internet!

`requests.get()` fetches data from a web address. APIs are special web addresses that return data instead of web pages. `response.json()` converts the data into Python dictionaries and lists.

---

**Step 3 (1 min): Working with different APIs**  

Let's try different types of web data:

```python
import requests

def get_joke():
    """Get a programming joke"""
    try:
        response = requests.get("https://official-joke-api.appspot.com/random_joke")
        
        if response.status_code == 200:
            joke_data = response.json()
            print("😄 Programming Joke:")
            print(f"Q: {joke_data['setup']}")
            print(f"A: {joke_data['punchline']}")
        else:
            print("❌ Couldn't get a joke")
    
    except requests.exceptions.RequestException:
        print("❌ Connection error")

def get_cat_fact():
    """Get a random cat fact"""
    try:
        response = requests.get("https://catfact.ninja/fact")
        
        if response.status_code == 200:
            cat_data = response.json()
            print("🐱 Cat Fact:")
            print(cat_data['fact'])
        else:
            print("❌ Couldn't get cat fact")
    
    except requests.exceptions.RequestException:
        print("❌ Connection error")

# Try different APIs
get_joke()
print()
get_cat_fact()
```

---

**Step 4 (1 min): Interactive web program**  

Build a program that lets users choose what to fetch:

```python
import requests
import random

def internet_explorer():
    """Interactive program to explore different web APIs"""
    
    apis = {
        "1": {
            "name": "Random Fact",
            "url": "https://uselessfacts.jsph.pl/random.json?language=en",
            "key": "text"
        },
        "2": {
            "name": "Programming Joke",
            "url": "https://official-joke-api.appspot.com/random_joke",
            "key": "setup"  # We'll handle jokes specially
        },
        "3": {
            "name": "Cat Fact",
            "url": "https://catfact.ninja/fact",
            "key": "fact"
        }
    }
    
    print("🌐 Internet Explorer!")
    print("What would you like to get from the internet?")
    
    while True:
        print("\nOptions:")
        print("1. Random Fact")
        print("2. Programming Joke")
        print("3. Cat Fact")
        print("4. Surprise Me!")
        print("5. Quit")
        
        choice = input("Choose (1-5): ")
        
        if choice in ["1", "2", "3"]:
            fetch_data(apis[choice])
        
        elif choice == "4":
            # Random choice
            random_api = random.choice(list(apis.values()))
            print("🎲 Surprise! Getting:", random_api["name"])
            fetch_data(random_api)
        
        elif choice == "5":
            print("👋 Thanks for exploring the internet!")
            break
        
        else:
            print("❌ Invalid choice!")

def fetch_data(api_info):
    """Fetch data from an API"""
    try:
        response = requests.get(api_info["url"])
        
        if response.status_code == 200:
            data = response.json()
            
            if api_info["name"] == "Programming Joke":
                print(f"😄 {api_info['name']}:")
                print(f"Q: {data['setup']}")
                print(f"A: {data['punchline']}")
            else:
                print(f"📄 {api_info['name']}:")
                print(data[api_info["key"]])
        else:
            print(f"❌ Couldn't get {api_info['name']}")
    
    except requests.exceptions.RequestException:
        print("❌ Connection error - check your internet!")

internet_explorer()
```

---

✅ **Takeaway:**

The internet is full of free APIs that provide data for your programs. You can get facts, jokes, weather, news, and much more to make your programs more interesting!

---

[[Day 17 🕰️ Time & Dates|< Day 17]] | [[Day 19 🎪 Mini Projects|Day 19 >]]