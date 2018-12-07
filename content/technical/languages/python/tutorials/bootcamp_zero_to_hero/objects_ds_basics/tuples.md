---
title: "Tuples"
date: 2018-12-07T22:36:10+05:30
weight: 6
pre: <b>6. </b>
chapter: false
---

- they are very similar to lists except they are __immutable__

- You can construct a tuple  using paranthesis with elements seperated by commas

```python
a = (1,2,3)
len(a) #3
```
- we can same methods as lists on tuples
- tuples can have different object types
- A tuple is a sequence like a sequence

```python
a = (1,2,3)
len(a) #3
a[-2] # 2

```
### Methods - only 2 methods
- if we want an index of element    __a.index()__
- If you want the frequency of an element use __a.count__


- the main advantage of tuples is we cannot mute it that means change it
```python
a = (1,1,2,5,4)
a.index(4) #4
a.count(1) #2
a[0] = "manoj" #error will come
b = [1,2,3] 
b[1] = "manoj" # will work coz they are mutable
```
- when we will use it
- if you want to not to change the order and we cannot edit them