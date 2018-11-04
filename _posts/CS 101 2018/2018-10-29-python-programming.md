---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Programming in Python

# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
  **Enroll** in our online community: [repl.it/classroom/](https://repl.it/classroom/invite/10YUXv2); **Online Python compiler:** [repl.it](https://repl.it)

# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [CS 101]
tags: [Programming Basics]
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

Python is a beautiful language. It's fun to learn, and its *syntax* (aka grammar) is simple yet elegant. Python is a popular choice for beginning programmers, 
yet powerful enough to back some of the world's most popular products and applications from companies such as NASA, Google, 
Microsoft, and Instagram. One of [Python's design goals](https://en.wikipedia.org/wiki/Python_(programming_language)#Features_and_philosophy) is 
to make the programming experience feel almost as natural as writing English.

- [Primitives](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#primitives): [numbers](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#numbers), [strings](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#strings), and [booleans](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#booleans)
- [User Inputs](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#user-inputs)
- [Control Statements](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#control-statements): [conditionals](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#if-statements) and [loops](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#loops)
- [Other sample programs](https://ramnauth.github.io/cs%20101/2018/10/29/python-programming/#other-sample-programs)

## Primitives
In social studies, the word "primitive" may refer to the earliest stage in the evolutionary development of something (e.g., *primitive* mammals). Or in the natural sciences, such as physics, "primitive" means "not developed/derived from anything else" (e.g., the *primitive* material of the universe).

Similarly, in *computer science*, **primitive** is either of the following:
- a **basic data type** provided by a programming language as a basic building block
- a **built-in data type** for which the programming language provides built-in support

A few primitives are numbers, strings, and booleans in Python.

### Numbers
Python has integers and floats. **Integers** are whole numbers, like 100, 345, and 718. 
**Floats**, however, are fractional numbers (aka numbers with decimals), like 1.005, 3.4567, 76.66667. 
You can use the `type` method to check the value of your number.

```py
>>> type(3)
<class 'int'>

>>> type(3.14)
<class 'float'>

>>> type(pi)
<class 'float'>
```

In the last example, `pi` is a **variable** name. Behind the scenes (aka in *memory*), `pi`'s value is `3.14`.

You can use the basic mathematical operators:
```py
>>> 3 + 3 		# addition
6

>>> 3 - 3		# subtraction
0

>>> 3 / 3		# division
1.0

>>> 3 % 2 		# modulus -- the remainder after integer division
1

>>> 3 * 3 		# multiplication
9

>>> 3 ** 3		# exponents -- base ** exponent
27

>>> num = 3		# storing a number into a variable called 'num'
>>> num = num - 1	# subtracting 1 from the current value of 'num'
>>> print(num)		# outputs the value of num
2

>>> num = num + 10 	# add 10 to the current value of 'num'
>>> print(num)
12

>>> num += 10 		# same thing as num = num + 10
>>> print(num)
22

>>> num -= 12		# same thing as num = num - 12
>>> print(num)
10

>>> num *= 10		# same thing as num = num * 10
>>> print(num)
100
```

Make sure to use parentheses to enforce precedence.
```py
>>> (2 + 3) * 5
25

>>> 2 + 3 * 5
17
```

### Strings
Remember we defined characters as anything you can type on the keyboard in one keystroke. It could be a letter, a number, a special symbol, and even a space key. 
A **string** is simply a string of characters. Python requires a string to be surrounded by either single or double quotes (`""` or `''`). 
```py
>>> print("Hello world!")
'Hello world!'

>>> message = "Hello!"
>>> type(message)
<type 'str'>
```

But what if you have a message with a quote in the middle of the string? Python needs help to recognize quotes as part of the English language and not the Python language.
```py
>>> "I don't think so."	# this works because it differentiates between single and double quotes
"I don't think so."

>>> 'I don"t think so'	# this works for the same reason
'I don"t think so'

>>> "She said \"no\" to me"	# this uses the escape character (the backslash) -- whatever comes after must stay in the string
'She said "no" to me'

# this produces a syntax error. Python understand the string 'I don', but doesn't know what to do with the rest of the sentence
>>> 'I don't think so'	
Traceback (most recent call last):
  File "python", line 1
    ""hello""
          ^
SyntaxError: invalid syntax
```

You can also join (**concatenate**) strings.
```py
>>> a = "flash"
>>> b = "light"
>>> a + b
'flashlight'

>>> "car" + "pet"
'carpet'
```

There are different string methods that you can use. For example, `upper()`, `lower()`, `replace()`, and `count()`.

```py
# upper() changes your string to all uppercase letters
>>> str = 'whoa!'
>>> str.upper()
'WHOA!'

# lower() changes your string to all lowercase letters
>>> str = 'WHOA!'
>>> str.lower()
'whoa!'

# replace() allows you to replace any character with another character
>>> str = 'accent'
>>> str.replace('n', 'p')
'accept'

# count() lets you know how many times a certain character appears in the string
>>> message = "Hello world"
>>> message.count('l')
3
```

### Booleans
**Boolean** values are either `True` or `False`. 
```py
>>> type(True)
<class 'bool'>

>>> type(True)
<class 'bool'>

>>> type("True")
<class 'str'>
```

**Comparison operations** generally produce a boolean value.
```py
# equality operator -- checks if a value is equal to another value with two equal signs
>>> 10 == 10 
True
>>> 10 == 5
False
>>> "hi" == "hi"
True
>>> "hi" == "hey"
False

# inequality operator -- checks if a value is not equal to another value
>>> 10 != 10 
False
>>> 10 != 11
True
>>> "hi" != "hi"
False
>>> "hi" != "hey"
True

# other comparison operators include >, <, >=, and <=
>>> 10 > 10 
False
>>> 10 < 11
True
>>> 10 >= 10
True
>>> 10 <= 11
True
>>> 10 <= 10 < 0
False
>>> 10 <= 10 < 11
True
>>> "hi" > "hi"
False
>>> "hi" > "he"
True # because 'i' has a larger ASCII value than the letter 'e'
```

Python also has **operators from Boolean logic**: `and`, `or`, `not`.
```py
>>> 3 > 5 or 5 < 6    # becomes False or True, which is True
True
>>> 3 > 5 and 5 < 6   # becomes False and True, which is False
False
>>> not True
False
>>> not (3 > 5)
True
>>> my_quiz_score >= 0 and my_quiz_score <= 100 
True	# true if my quiz score is between 0 and 100
```

## User Inputs
Sometimes, you may want to ask the user of your program to input something. 

In **Python v.3^**, there is **one** method that you can use to read data from the user: `input()`. You can store the results of `input()` into a variable. 

```py
name = input("What's you name? ")
age = input("What is your age? ")
print("Hello " + name + ".")
print("You are " + age + " years old.")
```

If I enter `Rebecca` for my name and `37` for my age, this program will output:
```
Hello Rebecca.
You are 37 years old.
```

### User Inputs in v.2.7
**Note:** in this class, we are using version 3 and above. This section is for the curious students wanting to know one reason why we upgraded.

There are two methods in Python that you can use to read data from the user: `raw_input()` and `input()`. You can store the results from them into a variable.

```py
>>> name = raw_input("What is your name? ") # raw_input reads your input as a string
>>> print("Your input is of type " + type(name))
Your input is of type <type 'str'>

>>> name = raw_input("What is your name? ")
>>> print("Hello " + name)
Hello 'Rebecca'

>>> age = input("What is your age? ") # input reads your input as an integer
>>> print("Your input is of type " + type(age))
Your input is of type <type 'int'>

>>> age = input("What is your age? ")
>>> print("You are " + age + " years old")
You are '37' years old.

>>> year = input("What year were you born? ")
>>> age = 2018 - year
>>> print("You are " + age + " years old")
You are '37' years old.
```

Note the main difference between `raw_input()` and `input()` is how Python reads your input. `raw_input()` reads your input as a string, whereas `input()` reads it as an integer. If you get them mixed up, you might get the following error:

<code>
>>> name = input("Enter your name: ")
>>> print("Hello " + name)

Enter your name:  Rebecca
Traceback (most recent call last):
  File "python", line 1, in <module>
  File "<string>", line 1, in <module>
NameError: name 'Rebecca' is not defined

This is because your program expects an integer, but you gave it a string (`"Rebecca"`).


## Control Statements

### If-Statements
The `if`-statement is used to check if a condition (or a boolean expression) is true. If the condition is true, the Python interpreter runs the block of statements called the if-block. If the statement is false, the interpreter skips the if-block and processes the next line or the else-block. An `else` statement is optional.

```py
num = 20
if num == 20:
	print("The number is 20")
else:
	print("The number is NOT 20")
```
This example outputs `The number is 20`.

```py
num = 21
if num == 20:
	print("The number is 20")
else:
	print("The number is NOT 20")
```
This example outputs `The number is NOT 20`.

You can also add an `elif` statement to add another condition to check for. 
```py
num = 21
if num == 20:
	print("The number is 20")
elif num > 20:
	print("The number is GREATER than 20")
else:
	print("The number is LESS than 20")
```
This example outputs `The number is GREATER than 20`.

### Loops
**Loops** are helpful when you want to do something several times. There are two kinds of loops used in Python -- the `for` loop and the `while` loop. 

`for` loops are traditionally used when you have a piece of code which you want to repeat *n* number of times. They are also commonly used to count and iterate over lists.
```py
# variable i starts at 0 and counts to 5, saying hello each time
for i in range(0, 5):
	print("Saying 'Hello' 5 times.")
```

`while` loops, like the `for` loop, are used for repeating sections of code. However, a `while` loop continues looping until it no longer fulfills a defined condition.
```py
num = 1

# condition - as long as num is less than or equal to 5, I'll keep saying hello
while num <= 5:
	print("Saying 'Hello' 5 times.")
	num += 1
```

Both of these examples output:
```py
Saying 'Hello' 5 times.
Saying 'Hello' 5 times.
Saying 'Hello' 5 times.
Saying 'Hello' 5 times.
Saying 'Hello' 5 times.
```

## Other sample programs
Adapted from Prof. League's [site](https://liucs.net/cs101f18/n7-python.html)

### Calculate wage and taxes
```py
wage = float(input('Enter your hourly rate: '))
hours = int(input('How many hours: '))
pay = wage * hours
if pay > 10000:
	print("You own 10% in taxes.")
	pay = pay * 0.9
print("Your pay is $" + str(pay)) # cannot concatenate a string and a float -- solution: cast (aka convert) the float into a string using the str() function
```

### A loop to count down
```py
n = 10
while n > 0:
	print(n)
	n = n - 10
message = "boom! blast off"
message = message.replace('o', 'ooo')
message = message.upper()
print(message)
```

### A loop to calculate a sum
```py
answer = 0
counter = 1 
n = input("Enter a number: ")
while counter <= n:
	print(counter)
	answer += counter
	counter = counter + 1
print("The sum of the numbers from 1 to " + str(counter) + " is " + str(answer))
```

### Repeat a fixed number of times
```py
count = 1
print(count)
for i in range(200):
	count = count * 2
	print(count)
```

### Repeat based on condition
This is a variation of the previous, where we find the first power of two that is larger than ten million.
```py
count = 1
while count <= 10000000
	count = count * 2
print(count)
```

### Factorial calculation
```py
n = int(input("Enter an integer >0: "))
k = 1
while n > 1:
    k = k * n
    n = n - 1
print(k)
```

### Euclid's greatest common divisor
```py
a = int(input("Enter an integer >0: "))
b = int(input("Enter another integer >0: "))
while a != b:
    if a < b:
        b = b - a
    else:
        a = a - b
print(a)
```

### Simulate coin flips
```py
import random
numFlips = 10000000
numHeads = 0

for i in range(numFlips):
    secretNumber = random.randrange(1,101)
    if secretNumber > 50:
        coinflip = "HEADS"
        numHeads = numHeads + 1
    else:
        coinflip = "TAILS"
    #print(coinflip)

percent = (numHeads / numFlips) * 100
print("There were", numHeads, "heads:",
      percent, "%")
```
