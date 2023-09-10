# Parameters vs Arguements

Parameters are the names used for inputs when *definintg* a function. Arguments are the names of the inputs supplied whena function is *called*.

```
# a and b are parameters
def add(a,b)
    return a + b

# 5 and 6 are arguments
sum = add(5,6)
```

___

# Default values for function arguments in Python

A default value is created by using the assignment (=) operator in the function signature.

```
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
```
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
# 4

3 ** 2 
# 9

## Incremental variables

In JavaScript or Go ++ syntax is used for incrementing a number variable
In Python we use "+=" operator instead.

Example:
```
star_rating = 4
star_rating += 1

# star_rating is now 5

```

### Other operators

```
# Subtractors
star_rating = 4
star_rating -= 1 

# Multiplication
star_rating = 4
star_rating *= 2

# Division
star_rating = 4
start_rating /= 2

```

## Example from assignment using -= subtractor to show incremental damange and return current health total:

```
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

```
print(16e3)
# Prints 16000.0

print(7.1e-2)
# Prints 0.071

```

## Underscores for readability

Python allows you to represent large numbers in the decimal format using underscores instead of commas to make it easier to read.

```
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

```
print(0b0001)
# Prints 1

print(0b0101)
# Prints 5

```

