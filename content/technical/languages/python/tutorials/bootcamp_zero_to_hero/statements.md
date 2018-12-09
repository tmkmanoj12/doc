---
title: Statements
date: 2018-12-08T08:22:18.000Z
weight: 3
pre: <b>3. </b>
chapter: false
---

- Other languages

```
if(a>b){
  a = 2
  b = 4
}
```

- In python

```python
if a>b :
  a = 2
  b = 4
```

- pyhton gets rid of **()** and **{}** and incorporates two things one colon(:) and a whitespace

- colon is used to end a statement and white space is ued to indent what happens in case of that statement has to be exceuted

- In other languages we use semicolons(;) to end a statement but python does not have semicolons instead it uses end of line as a end of statement

- beacuse readability is given more importance

# if condition

- notice here instead `elseif` there is `elif`

```python
one_condition = 2<3
if one_condition :
  print("1")
elif 5>2 :
  print("2")
else :
  print('else')
```

# for loop

- A for loop acts as an iterator in python , it goes through the items that are in a sequence or any other iterable item
- eg : strings, lists, tuples, dictionaries

```
for item in object : 
  do_stuff
```

```python
for item in [1,2,3,4,5] :
  print item+1
```

#### Modulo

- we use it to get remainder

```python
a = 10%3
```

- We can print even and odd numbers using for loop

```python
for item in [1,2,3,4,5,6,7]:
  if item%2 == 0:
    print('This is an even number')
  elif item%2 ==1 :
    print('This is a odd number')
  else :
    print("This is neither even nor odd")
```

- we can find the sum of elements in list , tuples

```python
sum = 0
for item in [1,2,3,4,5] :
  sum+= item
print(sum)
```
#### Unpacking tuples
```python
l = [(2,3),(4,3),(5,6)]
for (t1,t2) in l:
  print(t1)
```
- For above to work items have to uniform
- we can access the items inside of it using tuple unpacking
- Beacuse a lot of objects delivers iterables through tuples

#### Applying to Dictionary

```python 
l = {"k1":1,"k2" :2 ,"k3":2}
for item in l:
  print l # this will print only keys k2,k2,k1
```

- what if we want to get the values or both the keys and values
- in Python 2 we can use `.iteritems()`
- what it does it basically creates a generator

```python
d = {"k1":1,"k2" :2 ,"k3":3}
for key,value in d.iteritems():
  print(key , ':', value)
```
- In python 3 we can use `.items()`
- which is same as previous method

```python
d = {"k1":1,"k2" :2 ,"k3":3}
for key,value in d.items():
  print(key , ':', value)
```
- why generators worked in python 2
- beacause they are intorcued in earlier years of python
- basically _generators_ dont  store data in memory but yeilds the result as it goes through the itertable items
- originally python `items()` built a real list of tuples and returned that , this could potentially take a lot of memory
- After the generators were introducted to the language this method is reimplemeneted as a iterator generator method called __iteritems()__,
the original remains backward compatible
- Pyhton changes is that now __items()__ will return iterators and a list is never fully built and now __iteritems()__ is also gone since `items()` is doing that job

# While loop

- It is one of the general ways to perform iterration
- While statement will repeatedly excecute a single statement or a group of statements until the true value occurs

```python
x =0
while x<10:
  print("x is" ,x)
  x +=1
else:
  print("Finished !!!")
```
### Break Continue Pass

- we can use them to add additional functionality

- `break` it will break the nearest enclosing loop
- `continue` will continue executing the closest enclosing loop
-  `pass` does nothing at all

```python
# It is like

while test : 
  if cond1 :
    break
  if cond2 : 
    continue
else : 
print("Broke out")
```
- pass is like a null statement means nothing happiness
- difference betwwen  a comment and _pass_ is that comment is entirely ignored but the pass is not by the interpreter
- suppose if you want a for loop but dont want o implement it yest you can use pass statement , same goes with methods and class
### Range

- It will return a list of numbers
- we can find the type of object using `type()`
```python
a = range(0,10) # will give numbers from 0 to 9
# beacuse end is not included just like slicing
# if we want give only one arg
b = range(10) # will give numbers from 0 to 9
# we can also specify step size
c = range(0,10,2) # will give in intervals of 2
type(a) # will give a list
```

- In python 2 `range()` will return a list of numbers which includes storing them in memory
- what if we want a billion numbers
- we cannot do that with range , it will create problems
- so solution is `xrange()` which will return an _generator_
- genrator allows the genration of the objects and are provided at that instance , but it doesnt store every instance generated into memory
- that means genrate a billion numbers and provide them at that instance and toss them away
- so `xrange()` is a generator for numbers
- if you do `type(range(4))` will show _list_ , but for `type(xrange(4))` ill show _xrange_
- In python 3 there is no need for _xrange()_ because _range()_ is already a generator

### List comprehesions

- it allows us to build lists with different syntax , means using for loop
- Suppose if we want use for loop for constructing lists in traditional way

```python
l = []
for item in "manoj":
  l.append(item)
```

- which is a tedious way
- By list compreshension method we can use

```python 
list = [item for item in "manoj"]
```
- this means take the item from iteratble and fill the list with it
- examples
- build a list of sqaures for 10 numbers

```python 
squares = [item**2 for item in range(1,11)]
# we can even nest them

new_squares = [item**2 for item in (item**2 for item in range(1,10))]
```

- Convert celsius to fahrenheit

```
formula
fah = cel(9/5) + 32
```
```python
celsius = [10,20,40,50]
fah = [(temp)*(9/5.0) + 32 for temp in celsius]
```