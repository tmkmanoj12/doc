---
title: Scope
date: 2018-12-09T10:22:12.000Z
weight: 5
pre: <b>5. </b>
chapter: false
---

- How python deals with variable names
- when create a variable in python the variable name is stored in **namespace**
- variable names also have a scope
- This scope of a variable name decides the visibility of the variable to the other parts of code

```python
x = 50

def dummy():
    x =25
    return x
print x # will print 50
print dummy # will print 25
```

- so we have two different `x`
- so how does python know what `x` to refer to in each statement
- this is where scope comes(rules)

# Rules

- Name Assignments will create or change local names by default
- Name references search at most **4** scopes

  - local
  - enclosing
  - global
  - builtin

# LEGB

- checking will be from top to bottom in the below list

- (L : Local) : names assigned in a way within a fucntion(def or lambda) and not declared global in that function eg : In above rg `x` in dummy()

- (E : Enclosing Function Locals ) : Name in local of any and all enclosing functions(def or lambda) from inner to outer
- (G : Global) : Names assigned at the top level of a module file , or declared **global** in a def within a file
- (B :Built in) : names assigned in built in modules eg : `range, open , print etc`

```python
f = lambda x: x**2 # Here x is local to lambda function
name = "global name"
def Manoj():
    x = 20   # here x is local

def one():
    name = "manoj"
    def two():
        print 'Hello' + name
    two() # here name checks in enclosing def function same as closuer in JSs
    # output is Hello manoj

one()

print name # this will refer to global name

len("manoj") # here len refers to builtin
```

# local varibales

- when you decalre a variable name in a function it does not pollute the global function or enclosing functions - so even if we have same variable name in outside function our local var doesnot change that

- so all varibales have block scope , i.e their scope starts from the declaration of them to end of their current scope means if done inside a function it ends with function definition

```python
x = 50

def one(x):
  print x # here x is 50
  x = 25
  print x # here x is 25
one(x)

print x # here x is 50 unchanged
```

- suppose if you want to work on the global variable inside a function

- you have to use global keyword - means we are telling python that treat this variable as global and change accrodingly

```python
x = 50

def one():
  global x
  print x # here x is 50
  x = 25
  print x # here x is 25
one()

print x # here x is 25 changed
```
- we can use __globals()__ and __locals()__ to check what are your global and local variables are

- Everything in python is an object
- we can assign variables to fucntions just like numbers
