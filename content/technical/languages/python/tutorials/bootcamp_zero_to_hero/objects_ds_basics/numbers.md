---
title: "Numbers"
date: 2018-12-06T12:51:16+05:30
weight: 1
pre: <b>1. </b>
chapter: false
---

## Numbers

- lot of types of numbers in python

  - like integers : 1 ,3, 2
  - floating point numbers : 2.1, -1.23 , 4E2

- In python 2, it does classic division means decimal points gets truncated off

```python
3/2 = 1
```

- How can we make it do true division ,

  - atleast make sure one is floating point number

  ```python
  3.0/2 = 1.5
  3/2.0 = 1.5
  ```

  - Cast of them to float

    ```python
    float(3)/2 = 1.5
    ```

- In python 3 - it does true division

```python
3/2 = 1
```

- we can import some capabilities from python 3 to 2 using ****future****module

```python
from __future__ import division
```

- for finding power

```python
2**3 =8
```

- order of operation is **BODMAS**
- what if you want to specify order you can use order

```python
(2+3)*(10+4)
```

- assigning labels to objects to create variables , **a=5**

- The names you use when creating these labels need to follow a few rules:

  1. Names can not start with a number.
  2. There can be no spaces in the name, use _ instead.
  3. Can't use any of these symbols :'",<>/?|()!@#$%^&*~-+
  4. It's considered best practice (PEP8) that the names are lowercase.