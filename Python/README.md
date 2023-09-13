# Parameters vs Arguements

Parameters are the names used for inputs when *defining* a function. Arguments are the names of the inputs supplied whena function is *called*.

```python
# a and b are parameters
def add(a,b)
    return a + b

# 5 and 6 are arguments
sum = add(5,6)
```

___

# Default values for function arguments in Python

A default value is created by using the assignment (=) operator in the function signature.

```python
def get_greeting(email, name="there"):
    return f"Hello {name}, welcome! You've registered your email: {email}"

msg = get_greeting("lane@example.com", "Lane")
# Hello Lane, welcome! You've registered your email: lane@example.com

msg - get_greeting("lane@example.com")
# Hello there, welcome! You've registered your email: lane@example.com

```
If the second parameter is omitted, the default "there" value will be used in its place.


___

# Printing vs Returning

- pring(): A function that prints a value to the console. It does not return a value.
- return: A keyword that returns a value from a fucntion (back to the caller of the fucntion). It does not print anything to the console.

# Printing to Debug your code

Printing values and running your code in the console is a great way to debug your code. You can see what values are stored in various variables, find your mistakes, and fix them. Add print statements and run your code as you go! It's a great habit to get into to make sure that each line you write is doing what you expect it to do.

In the real world it's rare to leave print() statements in your code once you're done debugging. 

___

# Scope

Scope = "containers" 
When we create variables in a function (by giving names to our parameteres for example), the data is *not* available outside that function.

Example:
```python
### Global Scope
x = 5

### Parent Scope ("Container within a conatiner") 
def f():
    y = 10

### Parent Scope within a child scope
def g():
    z = 20
    def h():
        a = 1

```

___

# Python numbers

Integers = whole numbers, positive or negative
float = numbers with decimals

## Floor division

Python supports floor division
floor division functions like normal division *except* the result is "floored" afterward, which means the remainder is *removed*. This means the result is an integer instead of a float. 

Flooring numbers are always **rounded down.**

Normal division 
-  Integer / integer

Flooring
- Integer // integer

## Exponents in Python

2 ** 2
= 4

3 ** 2 
= 9

## Incremental variables

In JavaScript or Go ++ syntax is used for incrementing a number variable
In Python we use "+=" operator instead.

Example:
```python
star_rating = 4
star_rating += 1

# star_rating is now 5

```

### Other operators

```python
# Subtractors
star_rating = 4
star_rating -= 1 

# Multiplication
star_rating = 4
star_rating *= 2

# Division
star_rating = 4
start_rating /= 2

# Exponents
# reads as "three squared" or
# "three raised to the second power"
3 ** 2
# 9

```

### Example from assignment using -= subtractor to show incremental damange and return current health total:

```python
def get_hurt(current_health, damage):
    current_health -= damage
    return current_health


def test(current_health, damage):
    current_health = get_hurt(current_health, damage)
    print(f"Taking {damage} damage")
    print(f"Current health: {current_health}")
    print("=====================================")
    return current_health


def main():
    health = 1000
    print(f"Starting health: {1000}")
    health = test(health, 100)
    health = test(health, 60)
    health = test(health, 10)
    health = test(health, 3)


main()

```

## Scientific Notation

You can add the letter e or E followed by a positive or negative integer to specify that you're using scientific notation.

Scientific notation = a way of expressing numbers that are too large or too small to conveniently write normally.

The number following "e" specifies how many places to move the decimal to the right for positive number, or to the left for a negative number.

```python
print(16e3)
# Prints 16000.0

print(7.1e-2)
# Prints 0.071

```

## Underscores for readability

Python allows you to represent large numbers in the decimal format using underscores instead of commas to make it easier to read.

```python
num = 16_000
print(num)
# Prints 16000

num = 16_000_000
print(num)
# Prints 16000000

```

## Binary Numbers

Binary numbers = "base 2" numbers

Each 1 present in a binary number represents a greater multiple of 2.

Example:

- 0001 = 1
- 0010 = 2
- 0011 = 3
- 0100 = 4
- 0101 = 5
- 0110 = 6
- 0111 = 7
- 1000 = 8

In Python you can write an integer using binary syntax using the 0b prefix

```python
print(0b0001)
# Prints 1

print(0b0101)
# Prints 5

```

___

# Loops

Loops allow us to do the same operation multiple times without having to write it explicitly each time.

For example, I want to print numbers 0-9.

```python
for i in range (0, 5)
    print(i)

# Prints 0 1 2 3 4

```

This code says:

1. Start with i equals 0. (i in range (0))
2. If i is greater than or equal to 10 (range(0,10)), exit the loop.
3. Print i to the console. (print(i))
4. Add 1 to i. (range defaults to incrementing by 1)
5. Go back to step 2

The result is that numbers 0-4 are logged to the console in order.

We can change the incremental value, or direction of increments by using the following:

```python
for i in range (0, 10, 2):
    print (i)
# prints in increments of 2 for 0-10:
# o 
# 2
# 4
# 6 
# 8

for i in range (3, 0, -1)
    print (i)
# prints in increments down from 3-0, by 1
# 3
# 2 
# 1

```

To calculate the sum of all the odd numbers starting at 1 up to the given end number, you can modify the `sum_of_odd_numbers` function as follows:

```python
def sum_of_odd_numbers(end):
    total = 0
    for i in range(1, end + 1, 2):
        total += i
    return total
```

In this modified function:

1. We initialize the `total` variable to 0, which will be used to store the sum of odd numbers.
2. We use a `for` loop with `range(1, end + 1, 2)` to iterate through all odd numbers from 1 up to and including the `end` number. The `range` function generates a sequence of numbers starting from 1, ending at `end`, and stepping by 2, which ensures that only odd numbers are considered.
3. Inside the loop, we add each odd number `i` to the `total` variable.
4. Finally, we return the `total` variable, which contains the sum of all odd numbers in the specified range.

___

# Christmas Bonus Challenge

There are currently 102 employees, whose IDs are simply the numbers from 1 to number_of_employees. Loop over each employee id and:

- If the employee is a C-Level Executive add the c_level_bonus to the dollars_needed.
- If the employee is a manager add the manager_bonus to the dollars_needed.
- Otherwise, add the standard_bonus to the dollars_needed.

Use the variables given as necessary.

```python

number_of_employees = 102

c_level_bonus = 2000
manager_bonus = 1000
standard_bonus = 500

# C Level Executives
sarah_id = 1
mary_id = 2

# Managers
john_id = 6
bob_id = 44
joe_id = 18

dollars_needed = 0

# Don't touch above this line

for i in range(1, number_of_employees + 1):
    if i == sarah_id or i == mary_id:
        dollars_needed += c_level_bonus
    elif i == john_id or i == bob_id or i == joe_id:
        dollars_needed += manager_bonus
    else:
        dollars_needed += standard_bonus

# Don't touch below this line

print(f"{dollars_needed} dollars are needed to fulfill all bonuses")

# prints 55500 dollars are needed to fulfill all bonuses

```
___

# Lists in Python

Some languages call them "arrays", but in Python they are called lists.

Lists in python are declared using square brackets, with commas separating each item:

```python
# Example
inventory = ["Iron Breastplate", "Healing Potion", "Leather Scraps"]
```
Lists can contain items of any data type, in this example we have a list of strings.

Sometimes it may be hard to read when we are manually creating lists if all of the items are on one line of code. We can declare the array using multiple lines:

```python
flower_types = [
    "daffodill",
    "rose",
    "chrysanthemum"
]
```
## Indexing into lists

We can access items in a list by using their *index*. **Indexes start at 0 (the first item)** and increment by one with each successsive item.

```python
best_languages = ["JavaScript", "Go", "Rust", "Python", "C"]
print(best_languages[1])
# prints "Go", because index 1 was provided
```

## List length

The length of a list can be calculated using the **len()** function. 

```python
fruits = ["apple", "banana", "pear"]
length = len(fruits)
# Prints: 3
```
## List Updates

We can change items that exists at a given index. For example we can change `Leather` to `Leather Armor` in the `inventory` list in the following way:

```python
inventory = ["Leather", "Healing Potion", "Iron Ore"]
inventory[0] = "Leather Armor"
# inventory: ['Leather Armor', 'Healing Potion', 'Iron Ore']
```

## Appending in Python

It's common to create an empty list then fill it with values using a loop. We can add values to the end of a list using the `.append()` method:

```python
cards = []
cards.append("nvidia")
cards.append("amd")
# the cards list is now ['nvidia', 'amd']
```

## Pop Values

`.pop()` is the opposite of `.append()`. Pop removes the last element from the array and returns it for use. 

For example:

```python
vegetables = ["broccoli", "cabbage", "kale", "tomato"];
last_vegetable = vegetables.pop()
# vegetables = ['broccoli', 'cabbage', 'kale']
# last_vegetable = 'tomato'
```
## Counting the Items in a List

```python
items = [
    "Potion",
    "Leather Scraps",
    "Bread",
    "Iron Ore",
    "Light Leather",
    "Bread",
    "Shortsword",
    "Longsword",
    "Iron Mace",
    "Shortsword",
    "Shortsword",
]

potion_count = 0
bread_count = 0
shortsword_count = 0

# We can count how many times each of the following items show up in the list above using if/elif:

for i in range(0, len(items)):
    if items[i] == "Potion":
        potion_count += 1
    elif items[i] == "Bread":
        bread_count += 1
    elif items[i] == "Shortsword":
        shortsword_count += 1
        

print(f"You have {potion_count} potions in your inventory.")
print(f"You have {bread_count} pieces of bread in your inventory.")
print(f"You have {shortsword_count} shortswords in your inventory.")

# You have 1 potions in your inventory.
# You have 2 pieces of bread in your inventory.
# You have 3 shortswords in your inventory.
```

## No-Index Syntax

When we don't need to know the index, just the value:

```python
trees = ['oak', 'pine', 'maple']
for tree in trees:
  print(tree)

# Prints:
# oak
# pine
# maple
```
`tree`, the variable declared using the `in` keyword, directly accesses the value in the array rather than the index of the value. This is a cleaner way to write the code, as opposed to:

```python
trees = ['oak', 'pine', 'maple']
for i in range(0, len(trees)):
  print(trees[i])

# Prints:
# oak
# pine
# maple
```
Which achieves the same result.

## Finding the difference in an array

We can use loops over an indexes to determine the differences, and *index* where the values are different.

```python

old_character_levels = [1, 42, 43, 53, 12, 3, 32, 34, 54, 32, 43]
new_character_levels = [1, 42, 45, 54, 12, 3, 32, 38, 54, 32, 43]


# Because `old_character_levels` and `new_character_levels` are the same lengths, we can reuse `i` to index into both

for i in range(0, len(old_character_levels)):
    if old_character_levels[i] != new_character_levels[i]:
        print(i)

# Prints:
# 2
# 3
# 7 
```
# Modulo Operator in Python `%`

MODULO OPERATOR IN PYTHON
THE MODULO OPERATOR CAN BE USED TO FIND A REMAINDER:
For example, 7 modulo 2 would be 1, because 2 can be multiplied evenly into 7 at most 3 times:

`2 * 3 = 6`

Then there is 1 remaining to get from 6 to 7.

`7 - 6 = 1`

The modulo operator is the percent sign: %. It's important to recognize modulo is not a percentage though! That's just the symbol we're using.

```python
remainder = 8 % 3
# remainder = 2
An odd number is a number that when divided by 2, the remainder is not 0.
```

```python
odd_numbers = []

for i in range(0, 10):
    if i % 2 != 0:
        odd_numbers.append(i)

print(odd_numbers)
# Prints [1, 3, 5, 7, 9]
```
# Slicing Lists

The slicing operator allows us to cut and slice lists
Slicing operator is simply `:`

The syntax is as follows:
```python
my_list[ start : stop : step ]
```

For example:
```python
scores = [50, 70, 30, 20, 90, 10, 50]
# Display list
print(scores[1:5:2])
# Prints [70, 20]
```
The above reads as "give me a slice of the `scores` list from index 1, up to but no including 5, skipping every 2nd value.

## Omitting Sections

You can also omit various ("start","stop", or"step"). For example, `numbers[:3]` means "get all items from the start up to (but not including) index 3".

```python
scores = [50, 70, 30, 20, 90, 10, 50]
print(score[:3])

# Prints [50, 70, 30]
#Index:     0 - 1 - 2 | <-- stops before index 3
```
`numbers[3:]` means "get all items from index 3 to the end".

```python
scores = [50, 70, 30, 20, 90, 10, 50]
print(score[3:])

# Prints [20, 90, 10, 50]
#Index:  ...3 - 4 - 5 - 6 ] <-- starts at index 3 goes to end.
```

## Using only the "Step" Section

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
numbers[::2] # Gives [0, 2, 4, 6, 8]
```

## Negative Indices

Negative indicies count from the end of the list. For example, `numbers[-1]` gives the last item in the list, `numbers[-2]` gives the second last item, and so on.

```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
numbers[-3:] # Gives [7, 8, 9]
```
# List Deletion

Python has a built-in keyword `del` that deletes items from objects. In the case of a list, you can delete specific indexes or entire slices.

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]

# delete the fourth item
del nums[3]
print(nums)
# Output: [1, 2, 3, 5, 6, 7, 8, 9]

# delete the second item up to the fourth item
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
del nums[1:3] # [Index positions 1 *to* 3 but not 3]
print(nums)
# Output: [1, 4, 5, 6, 7, 8, 9]

# delete all elements
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9]
del nums[:]
print(nums)
# Output: []
```

# Tuples

Tuples are collections of data that are ordered and unchangeable. You can think of a tuple as a `List` with a fixed size. Tuples are created with round brackets.

```python
my_tuple = ("this is a tuple", 45, True)
print(my_tuple[0])
# this is a tuple
print(my_tuple[1])
# 45
print(my_tuple[2])
# True
```
While it's usually bad practice to store items of different types in a list it's not a problem with Tuples. (Because they have a fixed size, it's easy to keep track of which indexes store which types of data).

Tuples are often used to store very small groups (like 2 or 3 items) of data.

Example:

```python
dog = ("Fido", 4)
# Dog Name, Dog Age
```

- Multiple Tuples can be stored within a list.

```python
my_tuples = [("this is the first tuple in the list", 45, True),("this is the second tuple in the list", 21, False)]
print(my_tuples[0][0]) # this is the first tuple in the list
print(my_tuples[0][1]) # 45
print(my_tuples[1][0]) # this is the second tuple in the list
print(my_tuples[1][2]) # False
```
