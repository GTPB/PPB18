---
layout: page
title: Built-ins, namespaces, functions - Solutions
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
def triangle_area(b, h):
    A = (b*h)/2.0 # function  body
    return A      # function  body

print triangle_area(2.28, 3.55)
```

```python
def triangle_area(b, h):
    return (b*h)/2.0

print triangle_area(2.28, 3.55)
```

Back to the [lesson](8_functions.md)

<br/>

#### Solution to challenge #2

```python
def get_values(arg1, arg2):
    s = arg1 + arg2
    d = arg1 - arg2
    p = arg1 * arg2
    return s, d, p

print get_values(15, 8)
```
Back to the [lesson](8_functions.md)

<br/>

#### Solution to challenge #3

```python
import math

def distance(p1, p2):
    dist = math.sqrt((p1[0]-p2[0])**2 +
                     (p1[1]-p2[1])**2 +
                     (p1[2]-p2[2])**2)
    return dist

p1 = (43.64, 30.72, 88.95)
p2 = (45.83, 31.11, 92.04)

print "Distance:", distance(p1, p2)
```
<a href="https://github.com/ELIXIR-ITA-training/python_course/blob/master/day3/1-Functions/functions.md#challenge-3">back</a>

<br>

#### Solution to challenge #4

```python
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
      if line[0] == '>':
        return line

print return_header('SingleSeq.fasta')
```


Back to the [lesson](8_functions.md)

<br/>

#### Solution to challenge #5
```python
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
        if line[0] == '>':
            return line

filenames = ['SingleSeq1.fasta',
              'SingleSeq2.fasta',
              'SingleSeq3.fasta']

for name in filenames:
    print return_header(name)
```


Back to the [lesson](8_functions.md)

<br/>

#### Solution to challenge #6
one possible solution
```python
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
        if line[0] == '>':
            return line

filenames = ['SingleSeq1.fasta',
             'SingleSeq2.fasta',
             'SingleSeq3.fasta']

output = open("headers.txt", "w")

for name in filenames:
    output.write(return_header(name) + '\n')

output.close()
```
another possible solution

```python
def return_header(filename):
    fasta = open(filename)
    for line in fasta:
        if line[0] == '>':
          return line

filenames = ['SingleSeq1.fasta',
             'SingleSeq2.fasta',
             'SingleSeq3.fasta']
n = 0
for name in filenames:
    n = n + 1
    output = open("header" + str(n) + ".txt", "w")
    output.write(return_header(name))

output.close()
```


Back to the [lesson](8_functions.md)

<br/>

#### Solution to challenge #7

```python
def genbank2fasta(filename):
    name = filename.split('.')[0]
    InputFile = open(filename)
    OutputFile = open(name + ".fasta","w")
    flag = 0
    for line in InputFile:
        if line[0:9] == 'ACCESSION':
            AC = line.split()[1].strip()
            OutputFile.write('>'+AC+'\n')
        if line[0:6] == 'ORIGIN':
            flag = 1
            continue
        if flag == 1:
            fields = line.split()
            if fields != []:
                seq = ''.join(fields[1:])
                OutputFile.write(seq +'\n')
OutputFile.close()

filename = "ap006852.gbk"
genbank2fasta(filename)
```


Back to the [lesson](8_functions.md)

<br/>

### Back

Back to [main page](../index.md).
