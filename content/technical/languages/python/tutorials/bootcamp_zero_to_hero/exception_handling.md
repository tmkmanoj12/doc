---
title: Exception_handling
date: 2018-12-09T12:48:05.000Z
weight: 7
pre: <b>7. </b>
chapter: false
---

- For eg : syntax errors
- it is a specfic description of types of error
- Even statement is syntactically correct , while exceuting it may cause error
- just like try catch in other languages
- here our syntax is `try` , `except` , `finally`

```
try :
    do something
except Exception1 : 
    exceute this
except Exception2 :
    exceute this
else :
    if there is no exception exceute this
finally : 
    exceute afte reverything is done
```

- [Built In Exceptions](https://docs.python.org/2/library/exceptions.html)

```python
try:
    a = open("test1.txt")
except:
    print "hey file not there"
else : 
    print "Hey no error occured"
finally : 
    print "i am finally"
```

```python
try:
   2+"s"
except TypeError:
    print "hey type error"
else : 
    print "Hey no error occured"
finally : 
    print "i am finally"
```

```python
def askInt():
  try:
      val = int(raw_input("Please enter an integer"))
  except :
      print "hey you didnot entered integer"
      try: 
          k = int(raw_input("try again"))

      except :
          try :
              k = int(raw_input("last try"))
          except  :
              print "Maximum reached"
  else : 
      print "Hey no error occured"
  finally : 
      print "i am finally"
askInt()
```

- improve this method

```python 
def askInt():
  while True:
    try :
      val = int(raw_input("Please enter an integer"))
    except :
      print("Oops !! you didnot enter proper")
      continue
    else : 
      print "No error occured"
      break
    finally :
      print "This is finally"

```
