---
title: "Dictionaries"
date: 2018-12-07T22:11:33+05:30
weight: 5
pre: <b>5. </b>
chapter: false
---

- they are mappings in python
- we can think of it as `hash tables` or objects in `JS` in other languages

- Mappings are collection of objects that are sorted by a key unlike sequence that stores obejcts by relative sequence
- we can access an element in list by indexing
- what mapping is doing is its gonna start objects with key
- mappings are not gonna retain order

- Dictionary consists if a key and a value
- value can be any python object

```python
my_dict = {'key1': 'value','key2' : 'value2'}
```
### Accessing
```python
my_dict = {'key1': 'value','key2' : 'value2'}
my_dict["key1"] #outputs value
```
- based on value whih we access from the key we can have differnt methods on them

```python
a = {'name' : "manoj", "age":20}
a['name'][::-1] #for reversing
a["age"]-20 #subtract but it doesnot actually change the dictionary
a["age"] += 40 # changes
```

- we can create empty dictionary and create objects from it

```python
a = {}
a["name"]  =  "manoj"
a["age"] = 24
print(a) # {name : "manoj", age:24}
```
### Nesting 

``` python 
a = {}
a["name"]  =  "manoj"
a["age"] = 24
c = {'key' : {'nestedkey': a}}
# for getting age
print c["key"]["nestedkey"]["name"].upper()
```

### Methods

```python

a = {"k1" : "one","k2" : "two" , "k3" : "three"}

```

- For getting keys `a.keys()`
- For getting values `a.values()`
- they are out order beacuse they are mappings
- If you want a combiation of both `a.items`
    - this will return a list something called `tuples`

```python
a = {"k1" : "one","k2" : "two" , "k3" : "three"}
a.keys() # ["k1","k2","k3"]
a.values() #["two", "three" ,"one"]
a.items() # [('k3', 'three'), ('k2', 'two'), ('k1', 'one')]

```

- We can nest any way we want just like `JavaScript` Objects