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

- suppose you have 2 lists

```python
l1 = [1,2,3]
l2  = [4,5,6]
zip(l1,l1) #[(1,4),(2,5),(3,6)]

```
- the above will create a list of tuples

- suppose if we want the highest of two for each index in the lists

```python
x =[13123,223424,3534567,4123,624,2347,5468]
y = [1123,52456,513135,6512,536]

for pair in zip(z,y)
    print max(pair)
map(lambda pair : max(pair),zip(x,y)) # will create a list [13123, 223424, 3534567, 6512, 624]

```
- why only 5 were created beacuse priority will be given to the smaller list

```python

d1 = {'a' : 1 , 'b':2}
d2  = {'c': 3, 'd':4}

zip(d1,d2) # [('a', 'c'), ('b', 'd')]

```
- where the values gone ??
- beacuse iterating through the dictionaries will only give you the keys
- what if we want key values both - iteritems()

```python 
d1 = {'a' : 1 , 'b':2}
d2  = {'c': 3, 'd':4}

zip(d1.iteritems(),d2.iteritems()) # [(('a', 1), ('c', 3)), (('b', 2), ('d', 4))]

```

- suppose if you want only values you can use `itervalues()` in python 2 and `values()` in pyhton 3

```python

d1 = {'a' : 1 , 'b':2}
d2  = {'c': 3, 'd':4}

zip(d1.itervalues(),d2.itervalues()

```
- suppose if you want to switch the values in 1st dictionary to second values

```python
d1 = {'a' : 1 , 'b':2}
d2  = {'c': 3, 'd':4}

def switch_values(d1,d2):
    for d1_key,d2_value in zip(d1,d2.itervalues()):
        d1[d1_key] = d2_value
    print d1
```

- if one iterable is shorter than other shoter will be given preference and result will be of that length

#### Enumerate

- extremely useful function
- it allows you to keep a count while iterating through object

```python
l = ["a","b","c"]
count = 0
for item in l:
    print item
    print count
    count+=1
```
- the above is not necessary 
- enumerate returns a tuple

```python
for (count , item ) in enumerate(l):
    print (count,item)

for (count, item) in enumerate(l):
    if count>=2:
        break
    else :
        print item
```
## all() and any()

- they allow us to conviniently check for boolean matching in an interable

- all () - will return true if all the elements in the iterable are true
- any () - will return true if atleast one element is true

- our own implementation

```python

def all(iterable):
    for item in iterable:
        if not element:
                 False
    return True

def any(iterable):
    for item in iterable:
        if element : 
            return True
    else False
```
```python 
l= [True,False,True]
all(l) # False
any(l) # True
```

### complex()

- will return a complex number with real and imaginary part (a+ib)
- it ca take string or number to  to form complex number

- suppose if the first paramater is a string , then you dont call it second parameter
 - the second parameter can never be a string
 - Each argument may be a numberic type(inlcuding complex) and if you dont give imaginary it will default to zero which will act as numeric conversion like int or float

 ```python
 complex(2,3) #2+3j
 complex('2+3j')  # 2+3j