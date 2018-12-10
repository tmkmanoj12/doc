---
title: "Sets_booleans"
date: 2018-12-07T23:11:17+05:30
weight: 8
pre: <b>8. </b>
chapter: false
---

- sets are the unordered collection of the unique elements
- you can construct a set using _set()_
- it will look like a dictionary with no values but it is not
```python
a  = set()
a.add(1)
a.add(2)
a.add(2) # there will be no change
```
- we can convert a list with duplicate elements to unique using _set()_

```python
l = [1,1,1,1,1,1,1,3,3,3,3,3,5,5,5,45,5,4]
l = set(l)
print(l) # will give set(1, 3, 4, 5, 45) in sorted order
```
- sets are only concerned with unique elements

### Booleans

- they are `true` or `false`
- we can create using comaprision operaters __1>2__
- we can have `None` to an object that we dont have to reassign it yet

```python 
a = None
print(a)
```

### Comparision operators

We have same common comaprison oprators as other languages

```python
2<3
2<=3
2>=3
2>3
2==2
4!=3
2<>3 #this is same  as !=
```
### Chained COmparisions
- we have muliple comparision check in single line
- we can also have two opreators `and` , `or`

```python
1 < 2 < 3 # means 1<2 and 2<3
(1<2) and (2<3)

1<3>2 # means 1<3 and 3>2
1==2 or 2>1
```