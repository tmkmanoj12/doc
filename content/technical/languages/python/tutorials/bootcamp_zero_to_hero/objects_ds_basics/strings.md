---
title: Strings
date: 2018-12-06T07:25:29.000Z
weight: 2
pre: <b>2. </b>
chapter: false
---

- You can create by single quotes `''` or double quotes `""`
- It treates everything in a sentence as sequence
- Means **"Manoj Kumar"** every letter is a part of a sequence so that we can use indexing and slicing
- we can also have `"Manoj last name is 'kumar' "`
- we can do the opposite `'Manoj last name is "kumar"'`
- we can display it using **print** statement eg : `print "Manoj"`
- we can ask for new line symbol as `\n` like that we can have different characters such as `\t`

> python 2 vs python 3

- In v2 `print` is a statement
- In v3 `print` is a method `print()`
- in python 2 we can use `print()` by importing

```python
from __future__ import print_function
```

# String Methods

- length of a string

  - len("Manoj kumar")
  - it also counts spaces in the sequence

- we can refer to each element in a sequence by index

  - `"Manoj Kumar"[0]` gives `M`

- Slicing

  - slicing grabs everything upto the specified point
  - syntax is colon **:**
  - `Manoj Kumar[1:]` means take the string and grab everything from index : 1 onwards
  - Grab everything upto `3rd` index = `"Manoj Kumar"[:3]` , here upto 3rd index means not including 3rd index
  - grab everything `"Manoj Kumar"[:]` =
  - we can go backwards also - we have to give negative syntax
  - so in `"Manoj Kumar"` if `M` is _0_ index , then _-1_ index would be `r` , i.e 1 from backwards
  - Grab everything but last letter = `"Manoj Kumar"[:-1]` or `"Manoj Kumar"[:10]`

- we can use index and slicing by grabbing specified element using a step size - default step size in `1`

  - Grab everything and step size is _1_ = `"Manoj Kumar"[::1]` - for using step size you need to use double colons
  - so for grab everything in step size of _2_ = `"Manoj Kumar[::2]"`
  - Grab everything in reverse order = `"Manoj Kumar"[::-1]` , here _-1_ means specifying to traverse in reverse order

  - so to reverse a string

    ```python
    "Manoj Kumar"[::-1]
    ```

# String Properties

## Immutability

- means once it is created elements in it cant be changed
- so strings in python are immutable

  - `a= "Manoj"` ; `a[1] = "K"` **Throws an error**

- We can concatenate strings

  ```python
  "Manoj Kumar" + "Tatipamula"
  ```

- or we can altogether replace the variable

  - `a= "Manoj"` to `a="kumar"`

- We can use _Mutliplication symbol_ for string

  - `"M"*10` - it will repeat M _10_ times

## Bultin methods

- object in python has built in methods which we can apply on
- they are available as functions on objects
- `a= "Manoj"`

  - Upper Case

  ```python
  a.upper()
  ```

  - Lower Case

  ```python
  a.lower()
  ```

  - split an string into array by an element

    ```python
    a.split("a")
    ```
    - this will create an array by splitting based on a and **a** is not included
