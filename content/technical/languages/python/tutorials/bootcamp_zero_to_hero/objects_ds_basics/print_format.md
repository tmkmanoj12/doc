---
title: "Print_format"
date: 2018-12-06T15:39:07+05:30
weight: 3
pre: <b>3. </b>
chapter: false
---

- python 2 

__print__ statement is used to print the strings
- Print a string

```python
print "Manoj Kumar"
```
- Print a string vaiable along with a string

```python
a= "manoj"
print "My name is %s" %(a)
```
- Print a floating point variable

```python
a= 1.233
print "My name is %1.2f" %(a)
```
- In `1.2f` 2 is how many numbers to show past the decimal
- if you make 2 as 10 it will fill rest of absent decimals with 0
- _1_ is the total number of minimum digits that string should contain
- Suppose if you make _1_ to _10_ it will fill rest of the spaces with whitespaces

```python
a= 1.233
print "My name is %20.2f" %(a)
```
- Conversion format methods
- will convet any python object to string

```python
print "Convert to string %s" %(123)
```
- another formatting option we can use is __%r__

```python
print "Convert to string %r" %(123)
```
- they do the same thing but to achieve the result they use different functions
- _%s_ uses __str()__ and _%r_ uses __repr()__

- If you wanted to put more than one variable in string

```python
print "First %s Second %s Third %s" %("Hi","Manoj",3)
```
- Above-  order of variables matters
- Best way is _string.format_

```python
print "First {x} Second {y} Third {x}".format(x="inserted",y="manoj")
```
- here order doesnt matter

- In python 3

```python
print ("First {x} Second {y} Third {x}".format(x="inserted",y="manoj"))
```