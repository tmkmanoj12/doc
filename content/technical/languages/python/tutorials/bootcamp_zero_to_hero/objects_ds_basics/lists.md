---
title: "Lists"
date: 2018-12-06T17:07:15+05:30
weight: 4
pre: <b>4. </b>
chapter: false
---

- Strings are types of sequence in python
- lists are more generalised version of sequence
- lists are constructed with sqaure brackets and each element is seperated with commas

```python
my_list = [1,2,3]
```
- this is a list of integers
- lists can hold a different kind of object TypeScript

```python
my_list = [1,"string",3.341]
```

##Functions

- just like strings they have a length
- Length of a list

  ```python
    len([1,"string",3.341])
    
  ```
### Indexing and Slicing

```python
  a  = ["one",1,2,3]
  a[1] #output 1
  a[1:] # take everything from index - 1
  a[:3] # take everything upto index - 3 (excluding 3)
```

- You can concatenate lists like strings

```python

[1,2,3]+["one","two","three"]

```

- You can repeat the lists using __muliplication__ just like strings

```python

([1,2,3]+["one","two","three"])*2

```

- list can grow as long as we want
- they have no type constraint

### Methods

- __append__

  ```python 
    [1,2,3].append("append_me") # this wont work
    a = [1,2,3]
    a.append("append") # this works
  ```
- __pop__
 
  ```python 
    [1,2,3].pop() # this will work
    a = [1,2,3,4,5,6,7,8]
    a.pop() # this works
    ## we can also pop a specific index by default it is  -1
    a.pop(1)
  ```
  - after popping there will be no element in the list
- __sort__

  ```python
  [1,2,3].reverse() # will not work
  print([1,2,3].reverse()) # will not work gives output as None
  a  = [2,3,4]
  a.reverse()
  print(a) # this will permanently reverses the array unlike slicing which returns the sliced elements
  ```

#### We can have lists inside a lists

- we can form a matrix by having lists inside a list and it can do ery nested

```python
l1 = [1,2,3]
l2 = [4,5,6]
l3 = [7,8,9]
l = [l1,l2,l3]
print(l) # this is a matrix
# we can get elements like
inside_element = l[0][2]
```
- python has advanced feature called list comprehension and it allows for quick construction of lists - basically deconstructing `for` loop within brackets

```python 
l1 = [1,2,3]
l2 = [4,5,6]
l3 = [7,8,9]
l = [l1,l2,l3]
c = [row[0] for row in l]
print(c) # [1,4,7]
```
- this basicall means for every element in final list , grab the zeroth inde of that element
