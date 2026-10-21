# 📝 Worksheet: 03b - Containers → Functions

Do this worksheet **on paper, without a computer**. The point is to practice being the computer. Each section ends with an **🤖 Explain It** prompt: write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Trace a Loop

Fill in the table for this code:

```python
temps = [31, 45, 28, 52]
total = 0
count = 0
for t in temps:
    total += t
    if t <= 32:
        count += 1
```

| pass | `t` | `total` | `count` |
|------|-----|---------|---------|
| start | — | 0 | 0 |
| 1 |31 |31 |1 |
| 2 |45 |76 |1 |
| 3 |28 |104 |2 |
| 4 |52 |156 |2 |

Which **two** patterns are mixed together in this loop?  
`Answer:` Accumulator and counter

> 🤖 **Explain It:** Explain the difference between Accumulate, Count, and Filter as if you were talking to someone who has never programmed.
Accumulate takes a varibles and adds them all up to a total, count just sees how many varibles there are or how many fufill a certain requirement, and filter removes all varibles that don't fit a certain requirement and keeps those that do.
---

## 🧠 Section 2: Pick Your Weapon

| Scenario | Container | Why? |
|----------|-----------|------|
| Daily step counts for a month |List |Seperate totals stored together |
| A playing card (rank, suit) |Tuple |Two data points that represent one object |
| Username → password hash |Dictionary |A data point that points to some other data tied to it |
| Every distinct IP address in a log file |List |Seperate ip addresses that are stored together |
| Your class schedule, in order |List of dictionaries |Need to store several classes that also need to have multiple data about it, class name, time, and days |

> 🤖 **Explain It:** Pick the scenario you were *least* sure about and argue for a different container than the one you chose.
I was least sure about the class schedule. A list of tuples could work as it could store all the information about the class and the outer list keeps them distinct, but the dictionaries were probably a better choice because they can have the key associated with the values.
---

## 🧠 Section 3: Take It Apart

```python
course = {
    "title": "CMPS 3603",
    "students": [
        {"name": "Ana", "scores": [88, 92]},
        {"name": "Ben", "scores": [75, 81]}
    ]
}
```

Write the value after **each** step: 

1. `course["students"]` → {"name": "Ana", "scores": [88, 92]}, {"name": "Ben", "scores": [75, 81]}
2. `course["students"][1]` → {"name": "Ben", "scores": [75, 81]}
3. `course["students"][1]["scores"]` → [75, 81]
4. `course["students"][1]["scores"][0]` → 75

Write the expression that gets Ana's second score:  
`Answer:` course["students"][0]["scores"][1]

---

## 🧠 Section 4: Functions

1. What prints?

```python
def f(x):
    return x + 1

print(f(f(f(0))))
```

   `Answer:` 3

2. What prints? Explain why. 

```python
def shout(word):
    print(word.upper())

x = shout("hi")
print(x)
```

   `Answer:` HI   None. HI is printed in the funciton call but when x is printed there is nothing to print because the function does not return anything so x remains undefined.

3. Circle the **parameters** and underline the **arguments**:

```python
def greet(name, greeting):
    return greeting + ", " + name

greet("Ada", "Hello")
```
Parameters: name, greeting Arguments: "Ada", "Hello"
> 🤖 **Explain It:** In your own words, explain `print()` vs. `return`. Then explain why getting it wrong breaks a pipeline.
Print prints the argument and does not return any data, and return does return something allowing it to be assigned to a varible or printed from the call without printing being in the function. This being wrong could break a pipeline by not providing anything for a varible to be assigned and a value that needs to be saved is lost.
---

## 🧠 Section 5: Contracts and Tests

Write a contract for a function `longest_word(words)`:

```text
IN: A list of strings
OUT: A single string
DOES: Finds the word in the list of strings with the longest length
```

Write one test of each kind:

- Normal: ["The", "big", "brown", "dog", "is", "tired"]
- Boundary: ["Cat", "fat", "dog", "god"]
- Weird: [""]

---

## 🧠 Section 6: Draw the Pipeline

> "Given a list of prices, drop any that are `0` or less, add 8.25% tax to each, then find the total."

1. Name each function you'd need.
clean(), add_tax(), total()
2. For each one, write what goes **in** and what comes **out** (shape, not just "data").
clean()
"""
IN: A list of prices
OUT: A new list of prices
DOES: Removes negative and 0 prices
"""
add_tax()
"""
IN: List of prices
OUT: A new list of prices
DOES: Adds a tax to each price and places the output in a new list
"""
total()
"""
IN: List of prices
OUT: An int
DOES: Adds up all prices and gives a total.
"""
3. Draw the pipeline with arrows, labeling each arrow with the data's shape.
Prices ──► clean() ──► cprices ──► add_tax() ──► tprices ──► total() ──► total
      list         list        list         list         list        int                 
> 🤖 **Explain It:** Why is a pipeline of small functions easier to fix than one big block of code?
It is clearer where the error is in when one of the function fails to perform it tasks indicating which funciton is bugged.
