---
title: "Decorators"
date: 2018-12-10T20:47:26+05:30
weight: 10
pre: <b>10. </b>
chapter: false
---

- decorators can be thought as functions which modify the functionality of a function
 - we can get globals and locals anywhere by calling __globals()__ and __locals()__
 - those objects will comes as dictionary
 - we can get the keys of them by __globals().keys()__

 ```python

print  globals().keys()
```

```python
    def func():
        print locals() # {} beacuse there are no locals
        return 1

print func() #1
```
- in python each fuction will have its sperate namespace means scope

```python

def hello(name = "manoj"):
    print 'Hello ' + name
hello() # Hello manoj

# since everything is an object in python we can assign funtions to variables

greet = hello

greet() # Hello manoj
del hello
# what if i delete hello now 
# will hello work ? no
# will greet work ? yes beacuse greet is not attached to hello
greet() # Hello manoj
```

### Function within functions

- we can return functions too


```python
def hello(name = "manoj"):
    print "hello function is executed"
    def greet():
        return "\t this is inside greet"
    def welcome():
        return "\t this is inside welcome"
    print greet()
    print welcome()
    print "Control back to hello"
```
- here welcome and greet are not available outside in global

```python
def hello(name = "manoj"):
    print "hello function is executed"
    def greet():
        return "\t this is inside greet"
    def welcome():
        return "\t this is inside welcome"
    if name === "manoj":
        return greet
    else : 
        return welcome
x = hello()
print x # now x is pointing to greet function inside hello functions now 
```
#### Functions as arguments

```python

def hello()
    return "Hi Manoj"
def other(func):
    print "other is called"
    print func()

other(hello)

```
- so we can pass functions as object and use them with in other functions

### Decorators

```python
def new_decorator(func):
    def wrap():
        print "Before exceuting func"
        func()
        print "after exceuting func"
    return wrap

def func_needs_decorator():
    print "this function needs a decorator"

func_needs_decorator() ## prints

func_needs_decorator = new_decorator(func_needs_decorator)
# prints 
# before excetuning
# this function needs a decorator
# after exceting function


``` 
- So we changed the behaiviour of function
- decorator wrapped the normal function and modified its behaviour

- we can rewirte it using `@` decorator symbol

```python
def new_decorator(func):
    def wrap():
        print "Before exceuting func"
        func()
        print "after exceuting func"
    return wrap
@new_decorator # this line instead of func_needs_decorator = new_decorator(func_needs_decorator)
def func_needs_decorator():
    print "this function needs a decorator"
```