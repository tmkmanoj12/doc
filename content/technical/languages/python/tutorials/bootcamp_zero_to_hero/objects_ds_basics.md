---
title: Objects_ds_basics
date: 2018-12-03T14:08:45.000Z
weight: 2
pre: <b>2. </b>
chapter: false
---

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

- we can import some capabilities from python 3 to 2 using __ **future** __module

```python
from __future__ import division
```
- for finding power

```python
2**3 =8
```
- order of operation is __BODMAS__