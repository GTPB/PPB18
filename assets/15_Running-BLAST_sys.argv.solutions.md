---
layout: page
title: Pipelines - Solutions
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
import sys

print sys.argv

filename = sys.argv[1]

gbk = open(filename)

for line in gbk:
    if line[0:5] == 'LOCUS':
        print line

```

Back to the [lesson](15_Running-BLAST_sys.argv.md)

<br/>

#### Solution to challenge #2

```python
import subprocess

seqs = ['P00519', 'P05480', 'P12931']

for seq in seqs:
      command_line = ['blastp','-query',
                seq + '.fasta','-out',
                seq + '_blout', '-outfmt',
                '6','-db','nr.00']
      subprocess.call(command_line)
```

Back to the [lesson](15_Running-BLAST_sys.argv.md)

<br/>

#### Solution to challenge #3
```python
seqs = ['P00519', 'P05480', 'P12931']

out = open('blast_best_scores', 'w')

for seq in seqs:
      first_line = open(seq + '_blout').readline()
      column = first_line.split()
      out.write(column[0] + '\t' + column[2] + '\n')

out.close()
```
Back to the [lesson](15_Running-BLAST_sys.argv.md)

<br/>

### Back

Back to [main page](../index.md).
