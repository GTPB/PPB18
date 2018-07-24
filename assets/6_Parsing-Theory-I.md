Back to [main page](../index.md).



# Parsing data records I

Two sequence records in FASTA format:


```
>sp|P31946|1433B_HUMAN 14-3-3 protein beta/alpha OS=Homo sapiens
MTMDKSELVQKAKLAEQAERYDDMAAAMKAVTEQGHELSNEERNLLSVAYKNVVGARRWRVISSIEQKTERNEKKQQMGKEYREKIEAELQDICNDVLELLDKYLIPNATQPESKVFYLKMKGDYFRYLSEVASGDNKQTTVSNSQQAYQEAFEISKKEMQPTHPIRLGLALNFSVFYEILNSPEKACSLAKTAFDEAIAELDTLNEESYKDSTLIMQLLRDNLTLWTSENQGDEGDAGEGEN

>sp|P31946|1433B_HUMAN 14-3-3 protein beta/alpha OS=Homo sapiens
MTMDKSELVQKAKLAEQAERYDDMAAAMKAVTEQGHELSNEERNLLSVAYKNVVGARRWRVISSIEQKTERNEKKQQMGKEYREKIEAELQDICNDVLELLDKYLIPNATQPESKVFYLKMKGDYFRYLSEVASGDNKQTTVSNSQQAYQEAFEISKKEMQPTHPIRLGLALNFSVFYEILNSPEKACSLAKTAFDEAIAELDTLNEESYKDSTLIMQLLRDNLTLWTSENQGDEGDAGEGEN
```
---
Challenge #1


>
>Download the file from [here](data_and_scripts/Parsing/SingleSeq.fasta). Open the file `SingleSeq.fasta`, read its content line by line and print it
>
>
---


See the [Solution to challenge #1](6_Parsing-Theory-I.solutions.md)



---
Challenge #2

>
>Download the `SingleSeq.fasta` file from [here](data_and_scripts/Parsing/SingleSeq.fasta). Open the file, read its content line by line and write it to another file.
>
---

See the [Solution to challenge #2](6_Parsing-Theory-I.solutions.md)


### Writing different things depending on a condition

Read a sequence in FASTA format and print only the header of the sequence

```
>sp|P31946|1433B_HUMAN 14-3-3 protein beta/alpha OS=Homo sapiens
MTMDKSELVQKAKLAEQAERYDDMAAAMKAVTEQGHELSNEERNLLSVAYKNVVGARWRVISSIEQKTERNEKKQQMGKEYREKIEAELQDICNDVLELLDKYLIPNATQPESKVFYLKMKGDYFRYLSEVASGDNKQTTVSNSQQAYQEAFEISKKEMQPTHPIRLGLALNFSVFYEILNSPEKACSLAKTAFDEAIAELDTLNEESYKDSTLIMQLLRDNLTLWTSENQGDEGDAGEGEN
```

Making choices: The `if/elif/else` statements

```
if condition1 #if expression in condition1is TRUE
    statements1   #execute statements1
elif condition2 #else if expression in condition2is TRUE
    statements2 #execute statements2...
elif condition3 #etc...
...
…

else:
  statementN
```

Check these conditions:

- ` 'ACTC'[0] == 'C' `  is  True or false?
- ` 'ACTC'[0] == 'A' `  is  True or false?


Operators:

```
==    !=     =>    <=    >      <
```

The `if/elif/else` construct produces different effects compared with the use of a series of `if` conditions

```
  nucl = ['A','C','T','G']
  if 'A' in nucl: print 'A'
  elif 'C' in nucl: print 'C'
  elif 'T' in nucl: print 'T'
  else: print 'G'
```

```
nucl = ['A','C','T','G']
if 'A' in nucl: print 'A'
if 'C' in nucl: print 'C'
if 'T' in nucl: print 'T'
if 'G' in nucl: print 'G'
```

---
Challenge #3

>Download the file `SingleSeq.fasta` from [here](data_and_scripts/Parsing/SingleSeq.fasta). Read a sequence in FASTA format and print only the header of the sequence
>
>
```
>>sp|P31946|1433B_HUMAN 14-3-3 protein beta/alpha OS=Homo sapiens
MTMDKSELVQKAKLAEQAERYDDMAAAMKAVTEQGHELSNEERNLLSVAYKNVVGARWRVISSIEQKTERNEKKQQMGKEYREKIEAELQDICNDVLELLDKYLIPNATQPESKVFYLKMKGDYFRYLSEVASGDNKQTTVSNSQQAYQEAFEISKKEMQPTHPIRLGLALNFSVFYEILNSPEKACSLAKTAFDEAIAELDTLNEESYKDSTLIMQLLRDNLTLWTSENQGDEGDAGEGEN
```
>
>
---

See the [Solution to challenge #3](6_Parsing-Theory-I.solutions.md)

---
Challenge  #4

>
>Download the file `SingleSeq.fasta` from [here](data_and_scripts/Parsing/SingleSeq.fasta). Read the file in FASTA format and write to a new file only the header of the record.
>
---


See the [Solution to challenge #4](6_Parsing-Theory-I.solutions.md)


---
Challenge #5

>
>Download the file `SingleSeq.fasta` from [here](data_and_scripts/Parsing/SingleSeq.fasta). Read a file in FASTA format and write to a new file only the sequence (without the header).
>
---

See the [Solution to challenge #5](6_Parsing-Theory-I.solutions.md)


---
Challenge: Merge programs 4 and 5

> Download the file `SingleSeq.fasta` from [here](data_and_scripts/Parsing/SingleSeq.fasta). Read a file in FASTA format and write the header to a file and the sequence to a different one.
>
---

See the [Solution to merge challenge #4 and #5 ](6_Parsing-Theory-I.solutions.md)



---
Challenge #6

>Let’s increase the difficulty just a bit…
> Download the file `SingleSeq.fasta` from [here](data_and_scripts/Parsing/SingleSeq.fasta).
>+   Read a FASTA file line by line
>+   Save the header in a variable and the sequence in a different one
>+   Print header and sequence separately
>
---

See the [Solution to challenge #6](6_Parsing-Theory-I.solutions.md)


---
Challenge  #7

>+   Implement challenge #6 by counting the number of cysteine ("C") residues in the sequence
>+   Print separately header, sequence and the number of cysteine residues
>
---

See the [Solution to challenge #7](6_Parsing-Theory-I.solutions.md)




---
Challenge #8

>Download the file `SingleSeq.fasta` from [here](data_and_scripts/Parsing/SingleSeq.fasta).
>+ Read a file in FASTA format line-by-line.
>+   Print or write the **record** to a file only if the sequence is from Homo sapiens.
>
---

See the [Solution to challenge #8](6_Parsing-Theory-I.solutions.md)



---
Challenge  #9

>Very often in reality you will need to analyze several sequences….
>
> Download the Uniprot multiple sequence FASTA file `SwissProt-Human.fasta` [here](data_and_scripts/Parsing/SwissProt-Human.fasta). Consider the content of the file:  

```
SwissProt-Human.fasta

>sp|P31946|1433B_HUMAN 14-3-3 protein beta/alpha OS=Homo sapiens
MTMDKSELVQKAKLAEQAERYDDMAAAMKAVTEQGHELSNEERNLLSVAYKNVVGARRSSWRVISSIEQKTERNEKKQQMGKEYREKIEAELQDICNDVLELLDKYLIPNATQPESKVFYLKMKGDYFRYLSEVASGDNKQTTVSNSQQAYQEAFEISKKEMQPTHPIRLGLALNFSVFYYEILNSPEKACSLAKTAFDEAIAELDTLNEESYKDSTLIMQLLRDNLTLWTSENQGDEGDAGEGEN
>sp|P62258|1433E_HUMAN 14-3-3 protein epsilon OS=Homo sapiens
MDDREDLVYQAKLAEQAERYDEMVESMKKVAGMDVELTVEERNLLSVAYKNVIGARRASWRIISSIEQKEENKGGEDKLKMIREYRQMVETELKLICCDILDVLDKHLIPAANTGESKVFYYKMKGDYHRYLAEFATGNDRKEAAENSLVAYKAASDIAMTELPPTHPIRLGLALNFSVFYYEILNSPDRACRLAKAAFDDAIAELDTLSEESYKDSTLIMQLLRDNLTLWTSDMQGDGEEQNKEALQDVEDENQ
>sp|Q04917|1433F_HUMAN 14-3-3 protein eta OS=Homo sapiens GNYWHAHMGDREQLLQRARLAEQAERYDDMASAMKAVTELNEPLSNEDRNLLSVAYKNVVGARRSSWRVISSIEQKTMADGNEKKLEKVKAYREKIEKELETVCNDVLSLLDKFLIKNCNDFQYESKVFYLKMKGDYYRYLAEVASGEKKNSVVEASEAAYKEAFEISKEQMQPTHPIRLGLALNFSVFYYEIQNAPEQACLLAKQAFDDAIAELDTLNEDSYKDSTLIMQLLRDNLTLWTSDQQDEEAGEGN
...
...
...

```
>
> Write the record headers to a new file.
>
---

See the [Solution to challenge #9](6_Parsing-Theory-I.solutions.md)


---
Challenge  #10

>Download the Uniprot multiple sequence FASTA file `SwissProt-Human.fasta` [here](data_and_scripts/Parsing/SwissProt-Human.fasta).
>Read a multiple sequence FASTA file and write the sequences to a new file separated by a blank line
>
---

See the [Solution to challenge #10](6_Parsing-Theory-I.solutions.md)

---
Challenge #11

>Download the Uniprot multiple sequence FASTA file `SwissProt-Human.fasta` [here](data_and_scripts/Parsing/SwissProt-Human.fasta).
>Read a file in FASTA format and copy to a new file the records' Accession Numbers (AC).
>
---



See the [Solution to challenge #11](6_Parsing-Theory-I.solutions.md)


---
Challenge  #12

>Download the Uniprot multiple sequence FASTA file `SwissProt-Human.fasta` [here](data_and_scripts/Parsing/SwissProt-Human.fasta).   
>+   Read FASTA records from the file
>+   Count (and print) the cysteine residues in each sequence.
>
---


See the [Solution to challenge #12](6_Parsing-Theory-I.solutions.md)


---
Challenge  #13

>Download the Uniprot multiple sequence FASTA file `SwissProt-Human.fasta` [here](data_and_scripts/Parsing/SwissProt-Human.fasta). Read the file and write in a new file only the records from Homo sapiens.
>
---

See the [Solution to challenge #13](6_Parsing-Theory-I.solutions.md)


---
Challenge  #14 homework

>Download the Uniprot multiple sequence FASTA file `SwissProt-Human.fasta` [here](data_and_scripts/Parsing/SwissProt-Human.fasta).
>+  Read a multiple sequence file in FASTA format and only write to a new file the records the sequences of which start with a methionine ('M') and have at least two tryptophan residues ('W')
>
>First:
>
>+   Read a multiple sequence file in FASTA format and write to a new file only the records of the sequences starting with a methionine ('M')
>
>Then
>
>+    Read a multiple sequence file in FASTA format and write to a new file only the records of the sequences having at least two tryptophan residues ('W')
>
>Finally merge the two steps
>
---


See the [Solution to challenge #14](6_Parsing-Theory-I.solutions.md)


---
Challenge  #15 homework

>Download the `ap006852.gbk` file [here](data_and_scripts/Parsing/ap006852.gbk)
>Read a Genbank record and write to a file the nucleotide sequence in FASTA format. Extract and write to a file the gene sequence from the Candida albicans genomic DNA, chromosome 7, complete sequence (file ap006852.gbk)
>
> Try to write it in FASTA format:
```
>AP006852
ccactgtccaatggctcaacacgccaatcatcatacaatacccccaacaggaatcaccaa
agtactgatgcttctcactatcaatagtttgtactttcaccacacaatagcagatgatcc
atctaaatccaccttcctatcgatcgtgaccacccccataaaataggtcaactccataaa
cacctccatcaccaacgctagactcacaacccagaacatgttaatcaaccggtgggccaa
Gtaccgttgtagctctctcgtaaacacaagaaccaacaccaaacaacatactacaactga
...
...
```
>
---


See the [Solution to challenge #15](6_Parsing-Theory-I.solutions.md)


## Recap: parsing data records

+ Start by visually inspecting the file you want to parse

+   Identify the information you want to extract

+   Identify separators to select your information using if conditions

+   Use  lists if you have to compare data from different files

Back to [main page](../index.md).
