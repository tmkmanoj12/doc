---
title: Oops
date: 2018-12-09T10:53:15.000Z
weight: 6
pre: <b>6. </b>
chapter: false
---

- list is an object (everything is an object in python)
- we can have methods on list

```python
l = [1,2,3]
l.count() #3
```

- we can use **type()** to check the typeof object

```python
l = [1,2,3]
a = 2
b = "manoj"
tup = (1,2,3)
d = {"k1":1}
lamb = lambda x: x**2
def func():
  pass
type(a) # int
type(b) # str
type(tup) # tuple
type(d) # dict
type(l) # list
type(lamb) # function means object of type function
type(func) # function
```

- how can we create our own object types
- thats why we use `class` keyword

# class

- we can own object types using `class` keyword
- class is like blueprint that defines nature of the objects created with it
- from this classes we can construct instances
- an instance is a specific object created for a particular class

- eg : for list

```python
l = [1,2,3]
```

- `l` is an instance of the class `list`

## Creating a class

- by convention class names are captialized for first letter

```python
class Manoj(object):
  pass
x = Manoj()
type(x) # __main__.Manoj
```

- We can define **attributes** and **methods** inside a class
- attributes is the characteristic of an object eg : color of a car
- method is the action we can perform on an object eg : start is a method on car

- syntax for attribute

```python
self.name_of_attribute  = "manoj"
```

- there is a special method called `__int__()` which is used to instantiate or initialize the attributes of an object
- every single method in a class is going to have `self` word in it

```python
class Car(object):
  def __init__(self, model):
    self.model = model

xuv = Car(model = 'xuv')
```



- we gave `class` keyword , name of the class and gave `object` as argument

- then we start constructing methods
- as soon as you instantiate an object `__int__()` is called
- so `__int__()` should be your first method in a class just like `constructor` in other languages
- each method in the class definition begins the refernece to instance object , means you always start with `self` reference
- it doesnt have to be self keyword , we can use `this` also like JS , but always use this as the first parameter of every method

```python
class Car(object):
  def __init__(this, model):
    this.model = model

xuv = Car(model = 'xuv')
```
- when you dont give any arguments while creating object it will throw error saying 1 argument is missing , that means by default a reference to the object is passed as first argument always
- In python there is also a class object attribute and they are same for any instance of the class

```python
class Car(object):
  # class object attribute
  owner = 'manoj'
  def __init__(this, model,secondHand=False):
    this.model = model

xuv = Car(model = 'xuv')
```
- now we are not doing `self.owner` so python treats it as class level attributes
- here no matter what object we make from Car class owner will be manoj
- We can give object specific atributes inside a init method
- In python boolean is `True` instead of `true` in other languages same goes whith `False`
- We can also have default parameters same as JavaScript

### Methods

- they are used to perform operations with the attributes of our objects
- Methos are used in Encapsulation concept of OOPS
- Encapsulation : Allows you to divide responsibilities in programming and allows you to handle large apps
- we can think of  Methods as functions acting on objects

```python

class Circle(object):
  #class object attributes
  shape = 'round'
  pi = 3.14
  def __init__(self, radius=1):
    self.radius = radius
    self.perimeter = 2 * Circle.pi * self.radius
  def area (self):
    return Circle.pi*(self.radius**2)
  def set_radius(self, new_radius=1):
    """
    this will takes new radius and resets current radius
    """
    self.radius = new_radius

c1  = Circle(radius = 2)
print c1.pi # same as original
print "c1 radius = {x}".format(x=c1.radius)
print "c1 area = {x}".format(x = c1.area())

c2  = Circle(radius = 4)
print c2.pi # same as original
print "c2 radius = {x}".format(x=c2.radius)
print "c2 area = {x}".format(x = c2.area())

c1.set_radius(100)
print "c1  new radius = {x}".format(x=c1.radius)
print "c1  new area = {x}".format(x = c1.area())

```

## Inheritance

- It is a form of creating new classed using the classes which are already defined
- Newly formed classes are called derived classes
- parents are called base classes
- uses of inheritance is you can resuse the code and avoid duplication

```python

class Animal(object):
  def __init__(self):
    print "Animal Created"
  def whoAmI(self):
    print "Animal"
  def eat(self):
    print "Animal will eat"

class Dog(Animal):
  def __init__(self):
    Animal.__init__(self)
    print "Dog Created"
  def whoAmI(self):
    print "Iam dog"
  def bark(self):
    print "Woof !!!"
d = Dog()
d.whoAmI() #overided parent method
d.eat() # inherited parent method
d.bark() # has its own method
```

- In above code if we want to inherit the Animal Class object in Dog class object we have to pass Animal refernce in Dog class as argument instead of `object` so that it will inherit all the attributes and methods of parent  like usinf `extends` keyword in other languages
- In the special method `__int__` we need to call instantiate the Animal by calling `Animal.__init__(self)` which means inherit animal only for dog , notice here we are passing dog self as refernce , this is same as calling `super()` in other languages

### Special Methods

- classes in python can implemnt certain operations with special method names
- these methods are not  actaully  called directly  but by python specific language syntax

- when we make a list

- when we print list , python knows what to do with it
- when do `len(list)` pyhton knows what to do with it
- so python has some special methods on objects

```python

class Book(object):
  def __init__(self,author,pages):
    self.author = author
    self.pages = pages
    print "Book has been created"

b = Book("manoj",10)
print b # <__main__.Book object at 0x7f0648abd950>
```
- when we print a book we will get some confusing info saying where it is located in memory
- what if we want to know the contents of object 
- we have some special methods
  -`__str__ ` for printing
  - `__len__` for the length , but we can do whatever we want to output
  - `__del__` which will delete that object instance from memory

```python

class Book(object):
  def __init__(self,author,pages):
      self.author = author
      self.pages = pages
      print "Book has been created"
  def __str__(self):
      return "Author : {x} , pages: {y}".format(x=self.author,y=self.pages)
  def __len__(self):
      return self.pages
  def __del__(self):
      print "Book is deleted"
b = Book("manoj",10)
print b # Author : Manoj pages: 10
len(b) # 10
del(b) # Book is deleted
```