---
layout: page
title: Parsing data records II - Solutions
---

#### Solution to challenge #1

```
cancer_file = open('cancer-expressed.txt')

cancer_list = []

for line in cancer_file:
  AC = line.strip()
  cancer_list.append(AC)
print cancer_list
```

Back to the [lesson](7_Parsing-Theory-II.md)

<br/>

#### Solution to challenge #2

```
InputFile = open("SwissProtHuman.fasta","r")
AC_list = []
for line in InputFile:
  if line[0] == '>':
    fields = line.split('|')
    AC_list.append(fields[1])
print AC_list
```
Back to the [lesson](7_Parsing-Theory-II.md)

<br/>

#### Solution to challenge #3

```
cancer_file = open('cancer-expressed.txt')
human_fasta = open('SwissProt-Human.fasta')
Outfile = open('cancer-expressed.fasta','w')

cancer_list = []

for line in cancer_file:
  AC = line.strip()
  cancer_list.append(AC)

for line in human_fasta:
  if line[0] == '>':
    AC = line.split('|')[1]
    if AC in cancer_list:
      Outfile.write(line)

Outfile.close()
```


*We are not writing the whole record but the header line only*

Back to the [lesson](7_Parsing-Theory-II.md)

<br/>

#### Solution to challenge #4
One possible solution
```
cancer_file = open('cancer-expressed.txt')
human_fasta = open('SwissProt-Human.fasta')
Outfile = open('cancer_expressed.fasta','w')

cancer_list = []
seq = ''

for line in cancer_file:
  AC = line.strip()
  cancer_list.append(AC)

for line in human_fasta:
  if line[0] == '>':
    if seq:
      if AC in cancer_list:
        Outfile.write(header + seq)
      header = line
      AC = line.split('|')[1]
      seq = ''
  else:
    seq = seq + line

if AC in cancer_list:
  Outfile.write(header+seq)
```
A very elegant solution by David Judge

```

########################################################
### Pseudo-Code
###
### NO DATA CHECKING! ... Assuming perfect FASTA Format.
###
### Make a list of acc codes
###     Open the file with the cancer acc codes for reading
###     Make an empty list
###     Populate list with file contents
###     Close file
###
### Open Seq File for input.
### Open Cancer Sequence File for Output.
### Open Non-Cancer File for Output (could be NULL file).
###
### Trick this time is only to ever read a line in one place,
### then it can be used to control loop
###########################################################
###
### REPEAT reading a file until there are no more
###     if we have a header
###         Set Output file to reflect whether cancer or not
###
### Output the line whatever it is!
###
##############################################################

# Make the Cancer Acc code list.
acc_file=open ("cancer-expressed.txt");            # Open the Acc code file.
acc_list = [];                     # Make an empty list.
for Line in acc_file:              # Read in the Acc codes,
    acc_list.append(Line.strip()); # Stick each one in the list.
acc_file.close();                  # Close the Acc code file.

seq_infile = open ("SwissProt-Human.fasta"); # Open the Input File for reading.
seq_cancer = open("Cancer.fasta", "w");      # Open an Output file for the Cancer Seqeunces.
seq_other  = open("/dev/null","w")           # Open a NULL file for the Other Sequences.

for Line in seq_infile:
    if Line[0] == ">":                        # if a new header,
        if (Line.split("|")[1]) in acc_list:  # if cancer,
            Outfile = seq_cancer;             # point output to Cancer File
        else:                                 # if not cancer,
            Outfile = seq_other;              # point output to Other File (NULL)

    Outfile.write(Line);                      # Write line, whatever it is.

seq_infile.close(); # Close the Input File for reading.
seq_cancer.close(); # Close an Output file for the Cancer Seqeunces.
seq_other.close();  # Close a NULL file for the Other Sequences.


```


Another possible solution:
```
cancer_file = open('cancer-expressed.txt')
human_fasta = open('SwissProt-Human.fasta')
Outfile = open('cancer_expressed.fasta','w')

cancer_list = []

for line in cancer_file:
  AC = line.strip()
  cancer_list.append(AC)

for line in human_fasta:
  if line[0] == ">":
    field = line.split("|")
    AC = field[1]
    if AC in cancer_list:
      Outfile.write(line)
  else:
    if AC in cancer_list:
      Outfile.write(line)
Outfile.close()
```


Back to the [lesson](7_Parsing-Theory-II.md)

<br/>

Back to [first page](../index.md).
