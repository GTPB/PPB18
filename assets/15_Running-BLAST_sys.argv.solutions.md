---
layout: page
title: Pipelines - Solutions
---

#### Solution to challenge #1
```
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

```
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
```
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

Back to [first page](../index.md).

