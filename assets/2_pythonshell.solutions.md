---
layout: page
title: The Python Shell - Solutions
schemadotorg:
  "@context": http://schema.org/
  "@type": CreativeWork
  "genre": TrainingMaterial
  isPartOf:
      url: "https://gtpb.github.io/PPB18/"
      name: "PPB18 - Programming in Python for Biologists"
---

#### Solution to challenge #2
```python
from math import pi
R = 10.0
V = (4.0/3.0)*pi*(R**3)
print V
```
in this case we import a specific object from math instead of importing the whole `math` module <br>
Advantages: if the module is big and we need only one  function; we not using the "." syntax and the name of the variable pi is shorter!  

Back to the [lesson](2_pythonshell.md)

<br/>

#### Solution to challenge #3
```python
import math

x1 = 43.64
y1 = 30.72
z1 = 88.95

x2 = 45.83
y2 = 31.11
z2 = 92.04

dist = math.sqrt((x1-x2)**2 + (y1-y2)**2 + (z1-z2)**2)
print dist
```

Back to the [lesson](2_pythonshell.md)

<br/>

#### Solution to challenge #5
```python
import math

ATP = 3.5
ADP = 1.8
Pi = 5.0
R = 0.00831
T = 298
deltaG0 = -30.5

deltaG = deltaG0 + R * T * math.log(ADP * Pi / ATP)

print deltaG
```
Back to the [lesson](2_pythonshell.md)

<br/>

### Back

Back to [main page](../index.md).
