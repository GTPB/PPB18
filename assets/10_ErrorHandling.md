---
layout: page
title: Error Handling
schemadotorg:
  "@context": http://schema.org/
  "@type": CreativeWork
  "genre": TrainingMaterial
  isPartOf:
      url: "https://gtpb.github.io/PPB18/"
      name: "PPB18 - Programming in Python for Biologists"
---

## Exception handling


```python
try:
    f = open("test")
    for line in f:
        print line
except :
    f = open("test.txt")
    for line in f:
        print line
```

```python
try:  
    f = open("test.txt")
except :
    print "Cannot open the input file"
    raise SystemExit
else:
    for line in f:
      print line
```

```python
def main(data):
    print data

try:
    import sys
    data = sys.argv[1]
except :
    print "<usage: python my_script.py arg1>"
    raise SystemExit
else:
    main(data)
```

[**Built-in exceptions**](https://docs.python.org/2/library/exceptions.html)


<img src="img/ErrorHandling.png" alt="slot" style="width: 500px;"/>


```python

def main(data):
    print data

try:
    import sys
    data = sys.argv[1]
except ImportError:
    print "<usage: python my_script.py arg1>"
    raise SystemExit
else:
    main(data)
```

<br/>

### Back

Back to [main page](../index.md).
