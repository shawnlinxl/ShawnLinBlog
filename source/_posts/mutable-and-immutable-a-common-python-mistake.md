---
title: Mutability - A Common Python Mistake
date: 2022-07-06 11:56:47
tags: python
---

# Introduction 

I was trying to create a simple 2-D array in Python today. No numpy, no pandas, just the simpliest kind using the default list data structure.

Normally, to create a n by n 2-D array with all zeros, I would just do it through list comprehension:

```python
[[0 for i in range(n)] for j in range(n)]
```

Today I thought, what could possibly go wrong if I use the cool trick that works great with creating 1-D arrays?

If you are trying to create an 1-D array with all zeros, a common shortcut is

```python
[0] * n
```

Now, for 2-D array, I did

```python
[[0] * n] * n
```

However, when I run my program, it did not work as expected. For example, for a 3x3 array of all zeros, when I change array[0][0] to 1, I expect to see

```
1  0  0
0  0  0
0  0  0
```

Instead, I got:

```
1  0  0
1  0  0
1  0  0
```

# Mutability

So what happened? Let's talk about mutable objects first. Python mutability refers to being able to change an object. Simply put, a mutable object can be changed, but an immutable object cannot. Dictionaries, sets, and lists are mutable. When you change a mutable object, this is what happens:

```python
a = [0, 0, 0]
b = a
b[0] = 1
print(a)

> [1, 0, 0]
```

In our case, in the 2-D array, all rows are referring to the same mutable list object I created in the inner `[0] * n` code segment. Because lists are mutable, and array[1], array[2], ... are all referencing to the same list, when I changed the value of the list in one place, the change will propagate to all other places. This was not an issue when we use the same method to create 1-D arrays, as integer types are immutable.


# Reference

- https://www.codingem.com/python-mutability-explained/
- https://www.geeksforgeeks.org/python-using-2d-arrays-lists-the-right-way/
