# Coding

<a name="coding-beginner"></a>

<details>
<summary>What programming language do you prefer to use for DevOps related tasks? Why specifically this one?</summary><br><b>
</b></details>

<details>
<summary>Explain expressions and statements</summary><br><b>

An expression is anything that results in a value (even if the value is None). Basically, any sequence of literals so, you can say that a string, integer, list, ... are all expressions.

Statements are instructions executed by the interpreter like variable assignments, for loops and conditionals (if-else).
</b></details>

<details>
<summary>What is Object Oriented Programming? Why is it important?</summary><br><b>
</b></details>

<details>
<summary>Are you familiar with SOLID design principals?</summary><br><b>

SOLID design principals are about:

- Make it easier to extend the functionality of the system
- Make the code more readable and easier to maintain

SOLID is:

- Single Responsibility - A class should only have a single responsibility
- Open-Closed - An entity should be open for extension, but closed for modification. What this practically means is that you should extend functionality by adding a new code and not by modifying it. Your system should be separated into components so it can be easily extended without breaking everything.
- Liskov Substitution - Any derived class should be able to substitute the its parent without altering its corrections. Practically, every part of the code will get the expected result no matter which part is using it
- Interface segregation - A client should never depend on anything it doesn't uses
- Dependency Inversion - High level modules should depend on abstractions, not low level modules
  </b></details>

<details>
<summary>What are the four pillars of object oriented programming?</summary><br><b>
</b></details>

<details>
<summary>Explain recursion</summary><br><b>
</b></details>

<details>
<summary>Explain Inversion of Control</summary><br><b>
</b></details>

<details>
<summary>Explain Dependency Injection</summary><br><b>
</b></details>

<details>
<summary>Explain what are design patterns and describe three of them in detail</summary><br><b>
</b></details>

<details>
<summary>Explain big O notation</summary><br><b>
</b></details>

##### Common algorithms

<details>
<summary>Binary search:

- How it works?
- Can you implement it? (in any language you prefer)
- What is the average performance of the algorithm you wrote?</summary><br><b>

It's a search algorithm used with sorted arrays/lists to find a target value by dividing the array each iteration and comparing the middle value to the target value. If the middle value is smaller than target value, then the target value is searched in the right part of the divided array, else in the left side. This continues until the value is found (or the array divided max times)

[python implementation](coding/python/binary_search.py)

The average performance of the above algorithm is O(log n). Best performance can be O(1) and worst O(log n).
</b></details>

##### Code Review

<details>
<summary>What are your code-review best practices?</summary><br><b>
</b></details>

<details>
<summary>Do you agree/disagree with each of the following statements and why?:

- The commit message is not important. When reviewing a change/patch one should focus on the actual change
- You shouldn't test your code before submitting it. This is what CI/CD exists for.</summary><br><b>
  </b></details>

#### Strings

<details>
<summary>In any language you want, write a function to determine if a given string is a palindrome</summary><br><b>
</b></details>

<details>
<summary>In any language you want, write a function to determine if two strings are Anagrams </summary><br><b>
</b></details>

#### Integers

<details>
<summary>In any language you would like, print the numbers from 1 to a given integer. For example for input: 5, the output is: 12345</summary><br><b>
</b></details>

#### Time Complexity

<details>
<summary>Describe what would be the time complexity of the operations <code>access</code>, <code>search</code> <code>insert</code> and <code>remove</code> for the following data structures:</summary><br><b>

- Stack
- Queue
- Linked List
- Binary Search Tree
  </b></details>

<details>
<summary>What is the complexity for the best, worst and average cases of each of the following algorithms?:

- Quick sort
- Merge sort
- Bucket Sort
- Radix Sort</summary><br><b>
  </b></details>

#### Data Structures & Types

<details>
<summary>Implement Stack in any language you would like</summary><br><b>
</b></details>

<details>
<summary>Implement Hash table in any language you would like</summary><br><b>
</b></details>

<details>
<summary>What is Integer Overflow? How is it handled?</summary><br><b>
</b></details>

<a name="coding-advanced"></a>

<details>
<summary>Name 3 design patterns. Do you know how to implement (= provide an example) these design pattern in any language you'll choose?</summary><br><b>
</b></details>

<details>
<summary>Given an array/list of integers, find 3 integers which are adding up to 0 (in any language you would like)</summary><br><b>

```
def find_triplets_sum_to_zero(li):
    li = sorted(li)
    for i, val in enumerate(li):
        low, up = 0, len(li)-1
        while low < i < up:
            tmp = var + li[low] + li[up]
            if tmp > 0:
                up -= 1
            elif tmp < 0:
                low += 1
            else:
                yield li[low], val, li[up]
                low += 1
                up -= 1
```

</b></details>
