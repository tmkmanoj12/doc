---
title: "Files"
date: 2018-12-07T22:44:52+05:30
weight: 7
pre: <b>7. </b>
chapter: false
---

- Interacting with external files
- we will handle `.txt` files
- of we want to handle `.docx` , `.xlsx`

- we can open a file using __open('path')__
- we can read the file by __a.read()__
```python 
a = open('test.txt)
a.read()
```
- if you do a read again you will get an empty string , because it read the entire file and put the cursor at the end of file
- so we have to reset the cursor , to do that we can have __a.seek(cursorindex)__
- we can read the lines of the file by __a.readlines()__ , which will give list of element based on new line i.e splitting a string based on new line

- we have _magic function_ in jupyte for writing files

```
%%writefile new.txt
First Line
Second line
```
- Suppose if we want to iterate through lines we can use `for` loop

```python
a = open('test.txt')
a.read()
a.seek(0) # places the position at 0 index
a.readlines()
from __future__ import print_function
for line in open('test.txt'):
  print(line)
```
- __readlines()__ is good for small files but you have a `1 GB` text file it is not good because it will store the entire list returned by the readlines()
so use _read()_ instead
