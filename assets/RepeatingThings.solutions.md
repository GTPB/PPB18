---
layout: page
title: Repeating things - Solutions
schemadotorg:
  "@context": http://schema.org/
  "@type": CreativeWork
  "genre": TrainingMaterial
  isPartOf:
      url: "https://gtpb.github.io/PPB18/"
      name: "PPB18 - Programming in Python for Biologists"
---

#### Solution to challenge #1
```python
telomerase = open("telomerase.txt")

seq = telomerase.read()

print seq

for aa in seq:
  print aa
```
Back to the [lesson](RepeatingThings.md)

<br/>

#### Solution to challenge #2
```python
telomerase = open("telomerase.txt")

for line in telomerase:
  print line
```
Back to the [lesson](RepeatingThings.md)

<br/>

#### Solution to challenge #3
```python
telomerase = open("telomerase.txt")

seq = telomerase.read()

for aa in "ACDEFGHKILMNPQRSTVYW":
  aa_count = seq.count(aa)
  aa_freq = aa_count/float(len(seq))
  print aa, round(aa_freq, 3)
```
Back to the [lesson](RepeatingThings.md)

<br/>

### Back

Back to [first page](../index.md).
