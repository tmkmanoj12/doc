---
title: "Collection_module"
date: 2018-12-11T11:08:42+05:30
weight: 12
pre: <b>12. </b>
chapter: false
---

### Counters

- counter is actually a dictionary sub class which allows us to count hashable objects

```python
from collections import Counter
l = [1,2,2,1,3,4,5,5,3,3,45,6,7,1,2]
Counter(l) #Counter({1: 3, 2: 3, 3: 3, 4: 1, 5: 2, 6: 1, 7: 1, 45: 1})
```
- so the call to Counter method will count how many times each element exists
- so it returns a dictionary
- we can also count in  a string

```python

from collections import Counter
s = "sssddjsjdhsjdhasjdhajsaasaasjdakfsijfhjkehfjkh"
Counter(s)
```

- Count how many times each word shows up in a sentence

```python
from collections import Counter
s = "How may times the word show up up manoj manoj"
k = s.split()
out = Counter(k)


# Counter({'How': 1, 'manoj': 2, 'may': 1, 'show': 1, 'the': 1, 'times': 1, 'up': 2, 'word': 1}) 
# we can have different methods on out

out.most_common()
# will return a list of tuples
# [('up', 2), ('manoj', 2), ('word', 1), ('show', 1), ('may', 1), ('times', 1), ('How', 1), ('the', 1)] 

# we can ask for show 3 most common words
out.most_common(3)
# we can also get the sum of total words
sum(out.values())

# we can reset the all the counts by calling clear() on counter object

out.clear()

# we can call list() to get list of unique elements
list(out)
# we can convert it to a set by calling set()

set(out)
# we can convert into a dictionary
dict(out)

# we can call items() to  a list  of (elem,count) pairs
out.items()

# we can have a invert of out.items() means convert from a list of (e,cnt) pairs to dict and call a counter on it
Counter(dict(out.pairs()))

# we can have least common elements with string indexing syntax in negative
out.most_common()[:-n-1:-1] # will give n leasta common elements

# remove zero and negative counts
out =+ Counter(s)
 
```