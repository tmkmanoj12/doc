---
title: Iterators_generators
date: 2018-12-10T15:51:26.000Z
weight: 11
pre: <b>11. </b>
chapter: false
---

- generator function allows us to write a function that can send back the value and then later resume to pickup where it left off
- this type of function in python is a generator allowing us to generate a sequence of values over time
- main difference in syntax will be the use of `yield` statement
- generator functin will look like an normal function
- but the main difference is when a generator function is compiled they become the object that support an iteration protocol
- that means when they are called in your code they dont actually return a value and exit
- generator functions will automatically suspend and resume excecution and state around the last point of value generation
- the main advantage is instead of having to compute an entire series of values upfront , generator functions can be suspended, this is called state suspension

# Why use generators

- they useful for calculating large sets of results(particularly that involve calculations in the loops themselves) , where we dont want to allocate the memory yfor all the results at the same time

- many standard library functions in python 2 that return lists for example range are modified to generators in python 3

[About generators stack overflow](https://stackoverflow.com/questions/1756096/understanding-generators-in-python)

[About yield stack overflow](https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do)

```python
def gen_cubes(num):
    for item in range(num)
        yield num **3 # magic keyword for making function generator

gen_cubes(3) #0,1,8
```

- normal function implementation

```python
def gen_cubes(num):
    out = []
    for item in range(num)
        out.append(item**3)
    return out # if you give a very big num you will run into memory problems as entire list needs to be stored inside memory

gen_cubes(3) #0,1,8
```

- generate a fibanocci sequence

```python
def gen_fib(n):
    a=1
    b=1
    for item in range(n):
        yield a
        t =a
        a=b
        b =t+a
for item in gen_fib(10):
    print item
```

- we can rewrite this using tuple unpacking

```python
def gen_fib(n):
    a=1
    b=1
    for item in range(n):
        yield a
        a,b = b,b+a
for item in gen_fib(10):
    print item
```
- if we want to create in normal way

```python
def fibon(n):
    a=1
    b=1
    out = []
    for item in range(n):
        out.append(a)
        a,b = b,a+b
    return out
for item in fibon(1):
    print item
```

- if we call with large number we would have to hold that entire list in memory , we have to keep track of all the elements
- but with generators we only have to keep track of current item

#### Next function
- allows us to acess next element in the sequence

```python

def simple_gen():
 for x in range(3):
    yield x

g= simple_gen()

print next(g) #1

print next(g) # 2

```

- after yeilding all the values we have a stop iteration error
- why do we dont get this error when we use `for` loop because for loop automatically catches this error and stops calling

### iter function

- strings are iterables


- we can interate through a string but it doesnot mean that it is a iterator
- we can check this with `next()` - will give error
- string object supports iteration but we cannot direclty iterate over it as we could with generator function
- unless we use `iter()`


```python
s = "hello"
s_iter = iter(s)
# now we can call next
next(s_iter) # gives 'h' will go on till  it yeilds all and gives error

```