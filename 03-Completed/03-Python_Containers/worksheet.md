# 📝 Worksheet: 01 - Working with Data

Use this worksheet to review and reinforce your understanding of Python's core data containers. Each section ends with an **🤖 Explain It** prompt — write your explanation in your own words, then (optionally) paste it into an AI tutor and ask it to point out anything you got wrong or left out.

---

## 🧠 Section 1: Lists

1. What method adds an item to the end of a list?  
   `Answer:` append

2. How can you remove an item from a list by value? By position?  
   `Answer:` remove('value')  list.pop(index)

3. What's the result of this code?

```python
nums = [2, 4, 6]
nums.append(8)
print(nums)
```

   `Answer:` [2, 4, 6, 8]

4. What does `my_list[1:4]` return, given `my_list = [10, 20, 30, 40, 50]`?  
   `Answer:` 20, 30, 40

4a. Given `a = [1, 2]` and `b = [3, 4]`, what is the result of `a + b`? Of `a.append(b)`? Of `a.extend(b)`?  
   `Answer:` A new list [1, 2, 3, 4], [1, 2, [3, 4]], and the lists combined within a [1, 2, 3, 4] 

4b. Given `grid = [[1, 2], [3, 4]]`, how do you access the value `3`?  
   `Answer:` grid[1][0]

4c. List three different ways to remove an item from a list.  
   `Answer:` list.remove('value'), del list(index), and list.pop(index)

---

### ✏️ Task: List Practice

```python
# Create a list of your top 3 favorite foods.
# Add another food to the list.
# Remove one item and print the list.
food = [apple, orange, banana]
food.append(grape)
food.remove(banana)
print(food)
```

### ✏️ Task: Slicing and Sorting

```python
# Given: numbers = [42, 17, 8, 99, 23, 4]
# 1. Print the first three numbers using slicing.
# 2. Print the numbers sorted from smallest to largest.
# 3. Print the numbers sorted from largest to smallest.
print(numbers[0:3])
print(sorted(numbers))
print(sorted(numbers, reverse=True))
```

### ✏️ Task: Filtering

```python
# Given: temps = [55, 72, 90, 43, 88, 67, 101]
# Build a new list called "hot" containing only temps over 85.
# Print "hot".
hot = []
for t in temps:
   if t >= 85:
      hot.append(t)
print(hot)
```

### ✏️ Task: Combine Lists Three Ways

```python
# Given: morning = ['eggs', 'toast']
#        extras  = ['jam', 'coffee']
# 1. Use + to make a new list "breakfast" without changing "morning".
# 2. On a fresh copy of "morning", use .append(extras) and print the result.
#    Notice how many items the list has now, and why.
# 3. On another fresh copy, use .extend(extras) and print the result.
breakfast = morning + extras
morningCopy = morning
morning.append(extras)
morningCopy.extend(extras)
print(morningCopy)
```

### ✏️ Task: 2D List (grid)

```python
# board = [
#     [1, 2, 3],
#     [4, 5, 6],
#     [7, 8, 9],
# ]
# 1. Print the value in row 2, column 0.
# 2. Change the center value to 0.
# 3. Loop over the board and print each row on its own line.
print(board[2][0])
board[2][0] = 0
for row in board:
   for value in row:
      print(value, end=' ')
   print()
```

### ✏️ Task: Deleting Items

```python
# Given: queue = ['Ana', 'Ben', 'Cy', 'Dana', 'Eve']
# 1. Remove 'Cy' by value.
# 2. Use .pop() to remove and capture the last person into a variable "served".
# 3. Use del to remove the first person.
# 4. Print the remaining queue and "served".
queue.remove('Cy')
served = queue.pop(4)
del queue(0)
```
### ✏️ Task: Iterate by Index

```python
# Given: prices = [10, 20, 30, 40]
# 1. Use "for i in range(len(prices)):" to print each item as "0: 10", "1: 20", ...
# 2. Using the index, add 5 to every price in place, then print the list.
# 3. Rewrite step 1 using enumerate() instead.
for i in range(len(prices)):
   print(f'"{i}: {prices[i]}"')
for i in range(len(prices)):
   prices[i] += 5
print(prices)  
for i, price in enumerate(prices):
    print(f'"{i}: {price}"')
   
```

### 🤖 Explain It

In your own words: what's the difference between a list and a slice of a list? Is slicing a list the same as modifying it? And when you write `a.append(b)` versus `a.extend(b)`, what ends up in `a` each way?
A slice of a list is a portion of a list and does not require modifying only printing part of it. In append b is added to the end of a in as a single item in the list, whereas with extend it adds all elements of b as seperate elements of a.
---

## 🔒 Section 2: Tuples

5. What is a key difference between a list and a tuple?  
   `Answer:` Tuples are immutable.

6. Can you change the contents of a tuple once it is created? Why or why not?  
   `Answer:` No you cannot because they are immutable and cannot be changed after being defined.

7. What does `first, *rest = (10, 20, 30, 40)` assign to `first` and `rest`?  
   `Answer:` first = 10, *rest = (20, 30, 40)

---

### ✏️ Task: Tuple Practice

```python
# Create a tuple with your favorite 3 numbers.
# Unpack it into three variables and print each.
numbers = (7, 3, 9)
first, second, third = numbers
print(first, second, third)
```

### ✏️ Task: Unpacking with *rest

```python
# Given: race_times = (9.58, 9.63, 9.69, 9.71, 9.74)
# Unpack this into "winner" (the first time) and "others" (everything else).
# Print both.
winner, *others = times
print(winner)
print(others)
```

### ✏️ Task: Tuples as Dictionary Keys

```python
# Build a dictionary called "distances" where the keys are (city1, city2)
# tuples and the values are the distance in miles between them.
# Add at least two entries, then look up and print one of them.
distances = {
    ("New York", "Boston"): 215,
    ("Los Angeles", "Las Vegas"): 270,
}
cities = ("New York", "Boston")
print(f"The distance between {cities[0]} and {cities[1]} is {distances[cities]} miles.")
```

### 🤖 Explain It

In your own words: why does Python allow a tuple to be a dictionary key, but not a list? What property makes that possible?
It allows tuples to be a dictionary key because they are immutable and their value cannot be changed which allows them to be hashable. 
---

## 🔑 Section 3: Dictionaries

8. What does the `.get()` method do differently from accessing a key directly with `[]`?  
   `Answer:` The get method prevents crashing if the key does not exist unlike the [] method.

9. How do you loop through both keys and values in a dictionary?  
   `Answer:` You use the .items() method combined with unpacking in a for loop.

10. How would you remove a key from a dictionary and also capture the value it held?  
    `Answer:` Use the pop method

11. In a list of dictionaries like `people = [{'name': 'Ana'}, {'name': 'Ben'}]`, how do you get Ben's name?  
    `Answer:` You use [index] to access the specific person and then search with the key 'name'

12. If the same dictionary object is stored in both a list and another dictionary, and you change it through one, does the other see the change? Why?  
    `Answer:` Yes because they store a pointer to the list

---

### ✏️ Task: Dictionary Practice

```python
# Create a dictionary with keys: 'name', 'age', and 'hobby'.
# Print each key and value in the format "key: value".
user_info = {'name': 'Ana', 'age': 25,'hobby': 'Coding'}
for key, value in user_info.items():
    print(f"{key}: {value}")
```

### ✏️ Task: Build from Two Lists

```python
# Given: products = ['pen', 'notebook', 'eraser']
#        prices = [1.50, 3.25, 0.75]
# Build a dictionary mapping each product to its price.
# Print the total cost of all products (hint: sum the .values()).
products = ['pen', 'notebook', 'eraser']
prices = [1.50, 3.25, 0.75]
product_dict = dict(zip(products, prices))
total_cost = sum(product_dict.values())
print(f"Total Cost: ${total_cost:.2f}")
```

### ✏️ Task: Nested Dictionaries

```python
# Given:
# inventory = {
#     'apples': {'count': 50, 'price': 0.50},
#     'bananas': {'count': 30, 'price': 0.25},
# }
# Loop through inventory and print a line for each fruit like:
# "apples: 50 units at $0.50"
inventory = {
    'apples': {'count': 50, 'price': 0.50},
    'bananas': {'count': 30, 'price': 0.25},
}
for fruit, info in inventory.items():
    print(f"{fruit}: {info['count']} units at ${info['price']:.2f}")
```

### ✏️ Task: List of Dictionaries (table rows)

```python
# roster = [
#     {'name': 'Alex', 'major': 'CS'},
#     {'name': 'Ana',  'major': 'Math'},
#     {'name': 'Ben',  'major': 'History'},
# ]
# 1. Loop over roster and print "name - major" for each student.
# 2. Add a new student record to the list.
# 3. Build and print a list of just the names of everyone majoring in 'CS'.
for student in roster:
    print(f"{student['name']} - {student['major']}")
roster.append({'name': 'Chris', 'major': 'CS'})
cs_majors = [student['name'] for student in roster if student['major'] == 'CS']
print("CS Majors:", cs_majors)
```

### ✏️ Task: Update a Record by Row Number

```python
# Using the roster above:
# 1. Build a dict "by_row" mapping each row number to its record
#    (hint: {i: row for i, row in enumerate(roster)}).
# 2. Change the major of the student in row 2 to 'CS'.
# 3. Print roster[2] and explain why it changed too.
by_row = {i: row for i, row in enumerate(roster)}
by_row[2]['major'] = 'CS'
print("roster[2]:", roster[2])
```

### 🤖 Explain It

In your own words: what's the difference between `student['gpa']` and `student.get('gpa')` when `'gpa'` isn't in the dictionary? Which would you use, and when? Also: why does changing `by_row[2]` also change `roster[2]`?
Using .get when the key isnt in the dict prevents the program from crashing when it is not found whereas it would if it wasn't there in the [] method. It may be better to use [] if the key must be there and if it is not its better the program stops, and .get() is better when it is dynamic whether the key will or will not exist. 
Changing one changes the other because they point to the same location in memory.  
---

## 🚀 Section 4: Going Further (Optional)

These pair with the "🔥 Challenge" sections in the notebooks — skip if you haven't gotten there yet.

### ✏️ Task: List Comprehension

```python
# Rewrite this loop as a one-line list comprehension:
# cubes = []
# for n in range(6):
#     cubes.append(n ** 3)
```

### ✏️ Task: namedtuple

```python
# Create a namedtuple called "Book" with fields "title" and "author".
# Make one instance and print both fields by name.
```

### ✏️ Task: Word Counter

```python
# text = "to be or not to be that is the question"
# Build a dictionary counting how many times each word appears.
# (Try it by hand first, then check yourself with collections.Counter.)
```

### ✏️ Task: Parse Some JSON

```python
import json
raw = '''
{
  "course": "Programming for Data Science",
  "online": true,
  "instructor": null,
  "students": [
    {"name": "Alex", "grade": 91},
    {"name": "Ana",  "grade": 88}
  ]
}
'''
# 1. Use json.loads(raw) to turn this into Python objects.
# 2. Print the course name and the second student's grade.
# 3. Print the Python type of the value that came from "online" and from "instructor".
```

### ✏️ Task: Walk a GeoJSON FeatureCollection

```python
geo = {
    "type": "FeatureCollection",
    "features": [
        {"type": "Feature",
         "geometry": {"type": "Point", "coordinates": [-98.529, 33.878]},
         "properties": {"name": "Bolin Hall"}},
        {"type": "Feature",
         "geometry": {"type": "Point", "coordinates": [-98.531, 33.876]},
         "properties": {"name": "Moffett Library"}},
    ],
}
# Loop over geo["features"] and print each building's name with its
# latitude and longitude. Remember: coordinates are [longitude, latitude].
```

---

## 🧾 Submit Checklist

- [X] I practiced creating, slicing, sorting, and filtering lists.
- [X] I can explain the difference between `+`, `append()`, and `extend()`.
- [X] I built and traversed a nested (2D) list.
- [X] I removed list items with `remove()`, `pop()`, and `del`.
- [X] I looped by index with `range(len(...))` and with `enumerate()`.
- [X] I understand how tuples are different from lists, and why that makes them hashable.
- [X] I accessed, looped through, updated, and removed items from a dictionary.
- [X] I built a dictionary from two separate lists.
- [X] I worked with at least one nested dictionary.
- [X] I processed a list of dictionaries as table rows and updated a record by row number.
- [ ] I parsed JSON with `json.loads()` and walked a GeoJSON FeatureCollection.
- [X] I completed the "Explain It" prompts in my own words.
