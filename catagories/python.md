# Python

<a name="python-beginner"></a>

<details>
<summary>What are some characteristics of the Python programming language?</summary><br><b>

```
1. It is a high level general purpose programming language created in 1991 by Guido Van Rosum.
2. The language is interpreted, being the CPython (Written in C) the most used/maintained implementation.
3. It is strongly typed. The typing discipline is duck typing and gradual.
4. Python focuses on readability and makes use of whitespaces/identation instead of brackets { }
5. The python package manager is called PIP "pip installs packages", having more than 200.000 available packages.
6. Python comes with pip installed and a big standard library that offers the programmer many precooked solutions.
7. In python **Everything** is an object.

There are many other characteristics but these are the main ones that every python programmer should know.
```

</b></details>

<details>
<summary>What built-in types Python has?</summary><br><b>

    List
    Dictionary
    Set
    Numbers (int, float, ...)
    String
    Bool
    Tuple
    Frozenset

</b></details>

<details>
<summary>What is mutability? Which of the built-in types in Python are mutable? How can you show that a certain data type is mutable?</summary><br><b>

Mutability determines whether you can modify an object of specific type.

The mutable data types are:

    List
    Dictionary
    Set

The immutable data types are:

    Numbers (int, float, ...)
    String
    Bool
    Tuple
    Frozenset

You can usually use the function hash() to check an object mutability. If an object is hashable, it is immutable (although this does not always work as intended as user defined objects might be mutable and hashable).
</b></details>

<details>
<summary>In Python, functions are first-class objects. What does it mean?</summary><br><b>

In general, first class objects in programming languages are objects which can be assigned to variable, used as a return value and can be used as arguments or parameters.<br>
In python you can treat functions this way. Let's say we have the following function

```
def my_function():
    return 5
```

You can then assign a function to a variables like this `x = my_function` or you can return functions as return values like this `return my_function`
</b></details>

<details>
<summary>What is the result of running <code>[] is not []</code>? explain the result</summary><br><b>

It evaluates to True.<br>
The reason is that the two created empty list are different objects. `x is y` only evaluates to true when x and y are the same object.
</b></details>

<details>
<summary>Improve the following code:

```
char = input("Insert a character: ")
if char == "a" or char == "y" or  char == "o" or char == "e" or char =="u" or char == "i":
    print("It's a vowel!")
```

</summary><br><b>

```
if lower(input("Insert a character: ")[0]) in "aieou": # Takes care of multiple characters and small/Capital cases
    print("It's a vowel!")
```

OR

```
char = input("Insert a character: ") # For readablity
if lower(char[0]) in "aieou": # Takes care of multiple characters and separate cases
    print("It's a vowel!")
```

</b></details>

<details>
<summary>Explain inheritance and how to use it in Python</summary><br><b>

```
By definition inheritance is the mechanism where an object acts as a base of another object, retaining all its
properties.

So if Class B inherits from Class A, every characteristics from class A will be also available in class B.
Class A would be the 'Base class' and B class would be the 'derived class'.

This comes handy when you have several classes that share the same functionalities.

The basic syntax is:

class Base: pass

class Derived(Base): pass

A more forged example:

class Animal:
    def __init__(self):
        print("and I'm alive!")

    def eat(self, food):
        print("ñom ñom ñom", food)

class Human(Animal):
    def __init__(self, name):
        print('My name is ', name)
        super().__init__()

    def write_poem(self):
        print('Foo bar bar foo foo bar!')

class Dog(Animal):
    def __init__(self, name):
        print('My name is', name)
        super().__init__()

    def bark(self):
        print('woof woof')


michael = Human('Michael')
michael.eat('Spam')
michael.write_poem()

bruno = Dog('Bruno')
bruno.eat('bone')
bruno.bark()

>>> My name is  Michael
>>> and I'm alive!
>>> ñom ñom ñom Spam
>>> Foo bar bar foo foo bar!
>>> My name is Bruno
>>> and I'm alive!
>>> ñom ñom ñom bone
>>> woof woof

Calling super() calls the Base method, thus, calling super().__init__() we called the Animal __init__.

There is a more advanced python feature called MetaClasses that aid the programmer to directly control class creation.
```

</b></details>

<details>
<summary>Explain and demonstrate class attributes & instance attributes</summary><br><b>

In the following block of code `x` is a class attribute while `self.y` is a instance attribute

```
class MyClass(object):
    x = 1

    def __init__(self, y):
        self.y = y
```

</b></details>

<details>
<summary>What is an error? What is an exception? What types of exceptions are you familiar with?</summary><br><b>

```
#  Note that you generally don't need to know the compiling process but knowing where everything comes from
#  and giving complete answers shows that you truly know what you are talking about.

Generally, every compiling process have a two steps.
    - Analysis
    - Code Generation.

    Analysis can be broken into:
        1. Lexical analysis   (Tokenizes source code)
        2. Syntactic analysis (Check whether the tokens are legal or not, tldr, if syntax is correct)

               for i in 'foo'
                          ^
             SyntaxError: invalid syntax

        We missed ':'


        3. Semantic analysis  (Contextual analysis, legal syntax can still trigger errors, did you try to divide by 0,
          hash a mutable object or use an undeclared function?)

                 1/0
                ZeroDivisionError: division by zero

    These three analysis steps are the responsible for error handlings.

    The second step would be responsible for errors, mostly syntax errors, the most common error.
    The third step would be responsible for Exceptions.

    As we have seen, Exceptions are semantic errors, there are many builtin Exceptions:

        ImportError
        ValueError
        KeyError
        FileNotFoundError
        IndentationError
        IndexError
        ...

    You can also have user defined Exceptions that have to inherit from the `Exception` class, directly or indirectly.

    Basic example:

    class DividedBy2Error(Exception):
        def __init__(self, message):
            self.message = message


    def division(dividend,divisor):
        if divisor == 2:
            raise DividedBy2Error('I dont want you to divide by 2!')
        return dividend / divisor

    division(100, 2)

    >>> __main__.DividedBy2Error: I dont want you to divide by 2!
```

</b></details>

<details>
<summary>Explain Exception Handling and how to use it in Python</summary><br><b>
	
**Exceptions:** Errors detected during execution are called Exceptions.

**Handling Exception:** When an error occurs, or exception as we call it, Python will normally stop and generate an error message.</br>
Exceptions can be handled using `try` and `except` statement in python.

**Example:** Following example asks the user for input until a valid integer has been entered. </br>
If user enter a non-integer value it will raise exception and using except it will catch that exception and ask the user to enter valid integer again.

```py
while True:
    try:
        a = int(input("please enter an integer value: "))
        break
    except ValueError:
        print("Ops! Please enter a valid integer value.")

```

For more details about errors and exceptions follow this [https://docs.python.org/3/tutorial/errors.html](https://docs.python.org/3/tutorial/errors.html)

</b></details>

<details>
<summary>What _ is used for in Python?</summary><br><b>

1. Translation lookup in i18n
2. Hold the result of the last executed expression or statement in the interactive interpreter.
3. As a general purpose "throwaway" variable name. For example: x, y, \_ = get_data() (x and y are used but since we don't care about third variable, we "threw it away").
   </b></details>

<details>
<summary>Explain what is GIL</summary><br><b>
</b></details>

<details>
<summary>What is Lambda? How is it used?</summary><br><b>

A <code>lambda</code> expression is an 'anonymous' function, the difference from a normal defined function using the keyword `def`` is the syntax and usage.

The syntax is:

`lambda[parameters]: [expresion]`

**Examples:**

- A lambda function add 10 with any argument passed.

```py
x = lambda a: a + 10
print(x(10))
```

- An addition function

```py
addition = lambda x, y: x + y
print(addition(10, 20))
```

- Squaring function

```py
square = lambda x : x ** 2
print(square(5))
```

Generally it is considered a bad practice under PEP 8 to assign a lambda expresion, they are meant to be used as parameters and inside of other defined functions.

</b></details>

#### Properties

<details>
<summary>Are there private variables in Python? How would you make an attribute of a class, private?</summary><br><b>
</b></details>

<details>
<summary>Explain the following:

- getter
- setter
- deleter</summary><br><b>
  </b></details>

<details>
<summary>Explain what is @property</summary><br><b>
</b></details>

<details>
<summary>How do you swap values between two variables?</summary><br><b>

```
x, y = y, x
```

</b></details>

<details>
<summary>Explain the following object's magic variables:

- **dict**
  </summary><br><b>
  </b></details>

<details>
<summary>Write a function to return the sum of one or more numbers. The user will decide how many numbers to use</summary><br><b>

First you ask the user for the amount of numbers that will be use. Use a while loop that runs until amount_of_numbers becomes 0 through subtracting amount_of_numbers by one each loop. In the while loop you want ask the user for a number which will be added a variable each time the loop runs.

```
def return_sum():
	amount_of_numbers = int(input("How many numbers? "))
	total_sum = 0
	while amount_of_numbers != 0:
		num = int(input("Input a number. "))
		total_sum += num
		amount_of_numbers -= 1
	return total_sum

```

</b></details>

<details>
<summary>Print the average of [2, 5, 6]. It should be rounded to 3 decimal places</summary><br><b>

```
li = [2, 5, 6]
print("{0:.3f}".format(sum(li)/len(li)))
```

</b></details>

#### Python Lists

<details>
<summary>How to add the items of [1, 2, 3] to the list [4, 5, 6]?</summary><br><b>
x = [4, 5, 6]
x.extend([1, 2, 3])
</b></details>

<details>
<summary>How do you get the maximum and minimum values from a list? How to get the last item from a list?</summary><br><b>

```
Maximum: max(some_list)
Minimum: min(some_list)
Last item: some_list[-1]
```

</b></details>

<details>
<summary>How to get the top/biggest 3 items from a list?</summary><br><b>

```
sorted(some_list, reverse=True)[:3]
```

Or

```
some_list.sort(reverse=True)
some_list[:3]
```

</b></details>

<details>
<summary>How to sort list by the length of items?</summary><br><b>

```
sorted_li = sorted(li, key=len)
```

Or without creating a new list:

```
li.sort(key=len)
```

</b></details>

<details>
<summary>Do you know what is the difference between list.sort() and sorted(list)?</summary><br><b>

- sorted(list) will return a new list (original list doesn't change)
- list.sort() will return None but the list is change in-place

- sorted() works on any iterable (Dictionaries, Strings, ...)
- list.sort() is faster than sorted(list) in case of Lists
  </b></details>

<details>
<summary>Convert every string to an integer: <code>[['1', '2', '3'], ['4', '5', '6']]</code></summary><br><b>

```
nested_li = [['1', '2', '3'], ['4', '5', '6']]
[[int(x) for x in li] for li in nested_li]
```

</b></details>

<details>
<summary>How to merge two sorted lists into one sorted list?</summary><br><b>

```
sorted(li1 + li2)
```

Another way:

```
i, j = 0
merged_li = []

while i < len(li1) and j < len(li2):
    if li1[i] < li2[j]:
        merged_li.append(li1[i])
        i += 1
    else:
        merged_li.append(li2[j])
        j += 1

merged_li = merged_li + merged_li[i:] + merged_li[j:]
```

</b></details>

<details>
<summary>How to check if all the elements in a given lists are unique? so [1, 2, 3] is unique but [1, 1, 2, 3] is not unique because 1 exists twice</summary><br><b>
</b>

There are many ways of solving this problem:<br>
<code># Note: :list and -> bool are just python typings, they are not needed for the correct execution of the algorithm. </code>

Taking advantage of sets and len:

```
def is_unique(l:list) -> bool:
    return len(set(l)) == len(l)
```

This one is can be seen used in other programming languages.

```
def is_unique2(l:list) -> bool:
    seen = []

    for i in l:
        if i in seen:
            return False
        seen.append(i)
    return True
```

Here we just count and make sure every element is just repeated once.

```
def is_unique3(l:list) -> bool:
    for i in l:
        if l.count(i) > 1:
            return False
    return True
```

This one might look more convulated but hey, one liners.

```
def is_unique4(l:list) -> bool:
    return all(map(lambda x: l.count(x) < 2, l))
```

</details>

<details>
<summary>You have the following function

```
def my_func(li = []):
    li.append("hmm")
    print(li)
```

If we call it 3 times, what would be the result each call?

</summary><br><b>

```
['hmm']
['hmm', 'hmm']
['hmm', 'hmm', 'hmm']
```

</b></details>

<details>
<summary>How to iterate over a list in reverse order?</summary><br><b>

Method 1

```
for i in reversed(li):
    ...
```

Method 2

```
n = len(li) - 1
while n > 0:
    ...
    n -= 1
```

</b></details>

<details>
<summary>Sort a list of lists by the second item of each nested list</summary><br><b>

```
li = [[1, 4], [2, 1], [3, 9], [4, 2], [4, 5]]

sorted(li, key=lambda l: l[1])
```

or

```
li.sort(key=lambda l: l[1)
```

</b></details>

<details>
<summary>Combine [1, 2, 3] and ['x', 'y', 'z'] so the result is [(1, 'x'), (2, 'y'), (3, 'z')]</summary><br><b>

```
nums = [1, 2, 3]
letters = ['x', 'y', 'z']

list(zip(nums, letters))
```

</b></details>

#### Dictionaries

<details>
<summary>How to sort a dictionary by values?</summary><br><b>

```
{k: v for k, v in sorted(x.items(), key=lambda item: item[1])}
```

</b></details>

<details>
<summary>How to sort a dictionary by keys?</summary><br><b>

```
dict(sorted(some_dictionary.items()))
```

</b></details>

<details>
<summary>How to merge two dictionaries?</summary><br><b>

```
some_dict1.update(some_dict2)
```

</b></details>

##### Common Algorithms Implementation

<details>
<summary>Can you implement "binary search" in Python?</summary><br><b>

[Solution](coding/python/binary_search.py)
</b></details>

#### Python Files

<details>
<summary>How to write to a file?</summary><br><b>

```
with open('file.txt', 'w') as file:
    file.write("My insightful comment")
```

</b></details>

<details>
<summary>How to print the 12th line of a file?</summary><br><b>
</b></details>

<details>
<summary>How to reverse a file?</summary><br><b>
</b></details>

<details>
<summary>Sum all the integers in a given file</summary><br><b>
</b></details>

<details>
<summary>Print a random line of a given file</summary><br><b>
</b></details>

<details>
<summary>Print every 3rd line of a given file</summary><br><b>
</b></details>

<details>
<summary>Print the number of lines in a given file</summary><br><b>
</b></details>

<details>
<summary>Print the number of of words in a given file</summary><br><b>
</b></details>

<details>
<summary>Can you write a function which will print all the file in a given directory? including sub-directories</summary><br><b>
</b></details>

#### Python OS

<details>
<summary>How to print current working directory?</summary><br><b>
</b></details>

<details>
<summary>Given the path <code>/dir1/dir2/file1</code> print the file name (file1)</summary><br><b>
</b></details>

<details>
<summary>Given the path <code>/dir1/dir2/file1</code> print the name of the directory where the file resides (dir2)</summary><br><b>
</b></details>

<details>
<summary>Given the path <code>/dir1/dir2/file1</code> print the path without the file name (/dir1/dir2)</summary><br><b>
</b></details>

<details>
<summary>How do you execute shell commands using Python?</summary><br><b>
</b></details>

#### Python Regex

<details>
<summary>How do you perform regular expressions related operations in Python? (match patterns, substitute strings, etc.)</summary><br><b>

Using the re module
</b></details>

<details>
<summary>How to substitute the string "green" with "blue"?</summary><br><b>
</b></details>

<details>
<summary>How to find all the IP addresses in a variable? How to find them in a file?</summary><br><b>
</b></details>

<details>
<summary>You have the following list: <code>[{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}]</code>
  Extract all type of foods. Final output should be: {'mushrooms', 'goombas', 'turtles'}</summary><br><b>

```
brothers_menu =  \
[{'name': 'Mario', 'food': ['mushrooms', 'goombas']}, {'name': 'Luigi', 'food': ['mushrooms', 'turtles']}]

# "Classic" Way
def get_food(brothers_menu) -> set:
    temp = []

    for brother in brothers_menu:
        for food in brother['food']:
            temp.append(food)

    return set(temp)

# One liner way (Using list comprehension)
set([food for bro in x for food in bro['food']])
```

</b></details>

<details>
<summary>What is List Comprehension? Is it better than a typical loop? Why? Can you demonstrate how to use it?</summary><br><b>
</b></details>

#### Python Strings

<details>
<summary>How to extract the unique characters from a string? for example given the input "itssssssameeeemarioooooo" the output will be "mrtisaoe"</summary><br><b>

```
x = "itssssssameeeemarioooooo"
y = ''.join(set(x))
```

</b></details>

<details>
<summary>Find all the permutations of a given string</summary><br><b>

```
def permute_string(string):

    if len(string) == 1:
        return [string]

    permutations = []
    for i in range(len(string)):
        swaps = permute_string(string[:i] + string[(i+1):])
        for swap in swaps:
            permutations.append(string[i] + swap)

    return permutations

print(permute_string("abc"))
```

Short way (but probably not acceptable in interviews):

```
from itertools import permutations

[''.join(p) for p in permutations("abc")]
```

Detailed answer can be found here: http://codingshell.com/python-all-string-permutations

</b></details>

<details>
<summary>How to check if a string contains a sub string?</summary><br><b>
</b></details>

<details>
<summary>Find the frequency of each character in string</summary><br><b>
</b></details>

<details>
<summary>Count the number of spaces in a string</summary><br><b>
</b></details>

<details>
<summary>Given a string, find the N most repeated words</summary><br><b>
</b></details>

<details>
<summary>Given the string (which represents a matrix) "1 2 3\n4 5 6\n7 8 9" create rows and colums variables (should contain integers, not strings)</summary><br><b>
</b></details>

<details>
<summary>What is the result of each of the following?

```
>> ', '.join(["One", "Two", "Three"])
>> " ".join("welladsadgadoneadsadga".split("adsadga")[:2])
>> "".join(["c", "t", "o", "a", "o", "q", "l"])[0::2]
```

</summary><br><b>

```
>>> 'One, Two, Three'
>>> 'well done'
>>> 'cool'
```

</b></details>

<details>
<summary>How to reverse a string? (e.g. pizza -> azzip)</summary><br><b>

The correct way is:

```
my_string[::-1]
```

A more visual way is:<br>
<i>Careful: this is very slow</i>

```
def reverse_string(string):
    temp = ""
    for char in string:
        temp =  char + temp
    return temp
```

</b></details>

<details>
<summary>What is the output of the following code: <code>"".join(["a", "h", "m", "a", "h", "a", "n", "q", "r", "l", "o", "i", "f", "o", "o"])[2::3]</code></summary><br><b>

mario
</b></details>

<details>
<summary>Explain data serialization and how do you perform it with Python</summary><br><b>
</b></details>

<details>
<summary>How do you handle argument parsing in Python?</summary><br><b>
</b></details>

<details>
<summary>What is an iterator?</summary><br><b>
</b></details>

<details>
<summary>What is a generator? Why using generators?</summary><br><b>
</b></details>

<details>
<summary>What is <code>yeild</code>? When would you use it?</summary><br><b>
</b></details>

<details>
<summary>Explain the following types of methods and how to use them:

- Static method
- Class method
- instance method</summary><br><b>
  </b></details>

<details>
<summary>How to reverse a list?</summary><br><b>
</b></details>

<details>
<summary>How to combine list of strings into one string with spaces between the strings</summary><br><b>
</b></details>

<details>
<summary>You have the following list of nested lists: <code>[['Mario', 90], ['Geralt', 82], ['Gordon', 88]]</code> How to sort the list by the numbers in the nested lists?</code></summary><br><b>

One way is:

the_list.sort(key=lambda x: x[1])
</b></details>

<details>
<summary>Explain the following:

- zip()
- map()
- filter()</summary><br><b>
  </b></details>

#### Debugging

<details>
<summary>How do you debug Python code?</summary><br><b>

pdb :D
</b></details>

<details>
<summary>How to check how much time it took to execute a certain script or block of code?</summary><br><b>
</b></details>

<details>
<summary>What empty <code>return</code> returns?</summary><br><b>
</b>

Short answer is: It returns a None object.

We could go a bit deeper and explain the difference between

```
def a ():
    return

>>> None
```

And

```
def a ():
    pass

>>> None
```

Or we could be asked this as a following question, since they both give the same result.

We could use the dis module to see what's going on:

```
  2           0 LOAD_CONST               0 (<code object a at 0x0000029C4D3C2DB0, file "<dis>", line 2>)
              2 LOAD_CONST               1 ('a')
              4 MAKE_FUNCTION            0
              6 STORE_NAME               0 (a)

  5           8 LOAD_CONST               2 (<code object b at 0x0000029C4D3C2ED0, file "<dis>", line 5>)
             10 LOAD_CONST               3 ('b')
             12 MAKE_FUNCTION            0
             14 STORE_NAME               1 (b)
             16 LOAD_CONST               4 (None)
             18 RETURN_VALUE

Disassembly of <code object a at 0x0000029C4D3C2DB0, file "<dis>", line 2>:
  3           0 LOAD_CONST               0 (None)
              2 RETURN_VALUE

Disassembly of <code object b at 0x0000029C4D3C2ED0, file "<dis>", line 5>:
  6           0 LOAD_CONST               0 (None)
              2 RETURN_VALUE
```

An empty <code> return</code> is exactly the same as <code>return None</code> and functions without any explicit return
will always return None regardless of the operations, therefore

```
def sum(a, b):
    global c
    c = a + b

>>> None
```

</b></details>

<details>
<summary>How to improve the following block of code?

```
li = []
for i in range(1, 10):
    li.append(i)
```

</summary><br><b>

```
[for i in in range(1, 10)]
```

</b></details>

<details>
<summary>Given the following function

```
def is_int(num):
    if isinstance(num, int):
        print('Yes')
    else:
        print('No')
```

What would be the result of is_int(2) and is_int(False)?

</summary><br><b>
</b></details>

##### Data Structures & Types

<details>
<summary>Implement Stack in Python</summary><br><b>
</b></details>

<details>
<summary>Implement Hash table in Python</summary><br><b>
</b></details>

##### Python Testing

<details>
<summary>What is your experience with writing tests in Python?</summary><br><b>
</b></details>

<details>
<summary>What is PEP8? Give an example of 3 style guidelines</summary><br><b>

PEP8 is a list of coding conventions and style guidelines for Python

5 style guidelines:

    1. Limit all lines to a maximum of 79 characters.
    2. Surround top-level function and class definitions with two blank lines.
    3. Use commas when making a tuple of one element
    4. Use spaces (and not tabs) for indentation
    5. Use 4 spaces per indentation level

</b></details>

<details>
<summary>How would you check if two strings are equal? What about booleans?</summary><br><b>
</b></details>

<details>
<summary>How to test if an exception was raised?</summary><br><b>
</b></details>

<details>
<summary>What <code>assert</code> does in Python?</summary><br><b>
</b></details>

<details>
<summary>Explain mocks</summary><br><b>
</b></details>

<details>
<summary>How do you measure execution time of small code snippets?</summary><br><b>
</b></details>

<details>
<summary>Why one shouldn't use <code>assert</code> in non-test/production code?</summary><br><b>
</b></details>

#### Flask

<details>
<summary>You wrote you have experience with Django/Flask. Can you describe what is Django/Flask and how you have used it? Why Flask and not Djano? (or vice versa)</summary><br><b>
</b></details>

<details>
<summary>What is a route?</summary><br><b>
</b></details>

<details>
<summary>How do you manage DB integration?</summary><br><b>
</b></details>

#### zip

<details>
<summary>Given <code>x = [1, 2, 3]</code>, what is the result of list(zip(x))?</summary><br><b>

```
[(1,), (2,), (3,)]
```

</b></details>

<details>
<summary>What is the result of each of the following:

```
list(zip(range(5), range(50), range(50)))
list(zip(range(5), range(50), range(-2)))
```

</summary><br><b>

```
[(0, 0, 0), (1, 1, 1), (2, 2, 2), (3, 3, 3), (4, 4, 4)]
[]
```

</b></details>

#### Misc

<details>
<summary>Implement simple calculator for two numbers</summary><br><b>

```
def add(num1, num2):
    return num1 + num2


def sub(num1, num2):
    return num1 - num2


def mul(num1, num2):
    return num1*num2


def div(num1, num2):
    return num1 / num2

operators = {
    '+': add,
    '-': sub,
    '*': mul,
    '/': div
}

if __name__ == '__main__':
    operator = str(input("Operator: "))
    num1 = int(input("1st number: "))
    num2 = int(input("2nd number: "))
    print(operators[operator](num1, num2))
```

</b></details>

<a name="python-advanced"></a>

<details>
<summary>What data types are you familiar with that are not Python built-in types but still provided by modules which are part of the standard library?</summary><br><b>

This is a good reference https://docs.python.org/3/library/datatypes.html
</b></details>

<details>
<summary>Explain what is a decorator</summary><br><b>
</b>
<b>In python, everything is an object, even functions themselves. Therefore you could pass functions as arguments
for another function eg;

```
def wee(word):
    return word

def oh(f):
    return f + "Ohh"

>>> oh(wee("Wee"))
<<< Wee Ohh
```

This allows us to control the before execution of any given function and if we added another function as wrapper,
(a function receiving another function that receives a function as parameter) we could also control the after execution.

Sometimes we want to control the before-after execution of many functions and it would get tedious to write

<code> f = function(function_1())</code>
<code> f = function(function_1(function_2(\*args)))</code>

every time, that's what decorators do, they introduce syntax to write all of this on the go, using the keyword '@'.
</b>

</details>

<details>
<summary>Can you show how to write and use decorators?</summary><br><b>

<code>
These two decorators (ntimes and timer) are usually used to display decorators functionalities, you can find them in lots of
tutorials/reviews. I first saw these examples two years ago in pyData 2017. https://www.youtube.com/watch?v=7lmCu8wz8ro&t=3731s</code>

```
Simple decorator:

def deco(f):
    print(f"Hi I am the {f.__name__}() function!")
    return f

@deco
def hello_world():
    return "Hi, I'm in!"

a = hello_world()
print(a)

>>> Hi I am the hello_world() function!
    Hi, I'm in!
```

This is the simplest decorator version, it basically saves us from writting <code>a = deco(hello_world())</code>.
But at this point we can only control the before execution, let's take on the after:

```
def deco(f):
    def wrapper(*args, **kwargs):
        print("Rick Sanchez!")
        func = f(*args, **kwargs)
        print("I'm in!")
        return func
    return wrapper

@deco
def f(word):
    print(word)

a = f("************")
>>> Rick Sanchez!
    ************
    I'm in!
```

deco receives a function -> f
wrapper receives the arguments -> \*args, \*\*kwargs

wrapper returns the function plus the arguments -> f(\*args, \*\*kwargs)
deco returns wrapper.

As you can see we conveniently do things before and after the execution of a given function.

For example, we could write a decorator that calculates the execution time of a function.

```
import time
def deco(f):
    def wrapper(*args, **kwargs):
        before = time.time()
        func = f(*args, **kwargs)
        after = time.time()
        print(after-before)
        return func
    return wrapper

@deco
def f():
    time.sleep(2)
    print("************")

a = f()
>>> 2.0008859634399414
```

Or create a decorator that executes a function n times.

```
def n_times(n):
    def wrapper(f):
        def inner(*args, **kwargs):
            for _ in range(n):
                func = f(*args, **kwargs)
            return func
        return inner
    return wrapper

@n_times(4)
def f():
    print("************")

a = f()

>>>************
   ************
   ************
   ************
```

</b></details>

<details>
<summary>Write a decorator that calculates the execution time of a function</summary><br><b>
</b></details>

<details>
<summary>Write a script which will determine if a given host is accessible on a given port</summary><br><b>
</b></details>

<details>
<summary>Are you familiar with Dataclasses? Can you explain what are they used for?</summary><br><b>
</b></details>

<details>
<summary>You wrote a class to represent a car. How would you compare two cars instances if two cars are equal if they have the same model and color?</summary><br><b>
</b></details>

<details>
<summary>Explain Context Manager</summary><br><b>
</b></details>

<details>
<summary>Tell me everything you know about concurrency in Python</summary><br><b>
</b></details>

<details>
<summary>Explain the Buffer Protocol</summary><br><b>
</b></details>

<details>
<summary>Explain Descriptors</summary><br><b>
</b></details>

<details>
<summary>Do you have experience with web scraping? Can you describe what have you used and for what?</summary><br><b>
</b></details>

<details>
<summary>Can you implement Linked List in Python?</summary><br><b>
</b></details>

<details>
<summary>Can you implement Linux's <code>tail</code> command in Python? Bonus: implement <code>head</code> as well</summary><br><b>
</b></details>

<details>
<summary>You have created a web page where a user can upload a document. But the function which reads the uploaded files, runs for a long time, based on the document size and user has to wait for the read operation to complete before he/she can continue using the web site. How can you overcome this?</summary><br><b>
</b></details>

<details>
<summary>How yield works exactly?</summary><br><b>
</b></details>
