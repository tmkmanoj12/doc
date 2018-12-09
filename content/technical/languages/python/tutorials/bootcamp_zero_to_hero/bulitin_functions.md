---
title: "Bulitin_functions"
date: 2018-12-09T21:47:56+05:30
weight: 9
pre: <b>9. </b>
chapter: false
---


#### Map

- it takes two arguments 
    - function
    - sequence
- map will run the given function against each element in sequence

```python

def convertTemp(temp):
    return ((temp)*9/5.0) + 32

l = [10,20,30]
map(convertTemp,l)

```
- this is just like map in `JS`

- we can pass lambda expressions also

```python
map(lambda x: x*(9/5.0)+32),[10,20,30,40])
```

```python
a = [1,2,3]
b = [4,5,6]
c = [7,8,9]

map(lambda x,y: x+y,a,b)

```
- the main thing is it will take 0th index in a and 0th index of  b and apply lambda function and again it will take 1st index of a and 1st index of b and aply lambda function

- we can increase the number of parameters and input an extra array

```python
a = [1,2,3]
b = [4,5,6]
c = [7,8,9]

map(lambda x,y,z :x+y+z,a,b,c)

```

#### Reduce

- it is useful in conjuction with lamda expression
- it will also take two parameters 
    -  function 
    - sequence
- and it applies the function continuously to the each element in sequence

If seq = [ s1, s2, s3, ... , sn ], calling reduce(function, sequence) works like this:

- At first the first two elements of seq will be applied to function, i.e. func(s1,s2)
- The list on which reduce() works looks now like this: [ function(s1, s2), s3, ... , sn ]
- In the next step the function will be applied on the previous result and the third element of the list, i.e. function(function(s1, s2),s3)
- The list looks like this now: [ function(function(s1, s2),s3), ... , sn ]
- It continues like this until just one element is left and return this element as the result of reduce()

For eg : [47,11,42,13]

```python 
l = [47,11,42,13]
reduce(lambda x,y: x+y,l)
```

![](http://www.python-course.eu/images/reduce_diagram.png)

- Suppose if you want to find the greatest number in a list

```python
l = [1,10,4,3]
reduce(lambda a,b: a if a>b else b, l)

```

#### Filter

- it takes 
    - function
    - sequence
- same as map and reduce
- the function needs to return a boolean value
- the function needs to be applied to the each element of sequence
- if for the iteration the fucntion returns true then only that element will be included in result

```python

l = [1,2,3,45,6,12,14,13,47]

filter(lambda x: True if x%2 == 0 else False, l)
```

#### Zip

- zip makes an iterator that aggregates the elements from each iterables