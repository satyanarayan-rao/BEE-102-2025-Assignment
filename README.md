# BEE-102-2025-Assignment

This repository has programming question for CSE 2<sup>nd</sup> year students
(2023 admission), and CY 1<sup>st</sup> year students (2024 admission).

Few notes for completing the assignment:

1. All codes are to be written in Jupyter-Notebook or Jupyter-Lab.

## For CY students

### Normalized fragment length frequency (2 marks)

You are given a file with each line indicating where a DNA fragment has mapped
on the chromosome. Your goal is to count individual fragment lengths, and then
normalize it by the total count of all fragment lengths. Once you have the
normalized count, you will plot that using plotting packages in Python. X-axis
will be fragment length (unit: base pairs) and Y-axis will be labelled
"Narmalized Frequency [A.U.]". Fragment length can simply be calculated by
subtracting 2nd column from the 3rd.

### Multi-line sequence fasta to single-line fasta file (1 mark)

Fasta file format is shown below. Many times, it is annoying to find sequences
of interest because of fix-width format, i.e., if 60 character fix-width file
is there then only except the header (starting with `>`) of the sequence each
line will have 60 characters. So, if a sequence is of width 600, then it would
be written in 10 lines. Your goal is convert this format to a format with
header in a single line followed by its sequence in a single line. 

Example input:

```
>this is a long sequence
GTTCTACTTGCGGACGGATCGTAACCGAACTGGCCCGGATCTTTCATCCTCATGTAGAT
GCACAAAAGGTTCATCTAATAGTACTACCTCTTCTACTCGC
>this is okay
GGTTCATCTAATAGTACTACCTCTTCTACTCGC 

```

If you search for `TAGATGC`, you will not find that in a single line because of
the boundary issue. 

Example output: 

```
>this is a long sequence
GTTCTACTTGCGGACGGATCGTAACCGAACTGGCCCGGATCTTTCATCCTCATGTAGATGCACAAAAGGTTCATCTAATAGTACTACCTCTTCTACTCGC
>this is okay
GGTTCATCTAATAGTACTACCTCTTCTACTCGC 

```

NOTE: points to consider
-----
If you will use `list` data structure to store sequence to print later, imagine
how your code would handle 220 Mega bases (length of human `chr1`) if you are
working with human chromosomes. If you use list, then you will earn lesser
point that those who didn't.


### Building Markov transition matrix (2 marks)

You have learned important differences between simple dinucleotide frequency
model and Markov models. Your goal is to build one from the input sequence. In
the Jupyter notebook, you should print the transition matrix. 


### V-plot (2 marks)

You can imagine when a protein binds to DNA, then that region will be protected
by nucleases (a type of enzyme that cleaves DNA). If you are to plot the
protected fragments at protein binding sites, it will take a V-form. Your goal
is to show this V-formation using the input data. 


### Writing codes for linear regression (2 marks)

Design data yourself, 

### Reading a PDB file to output protein sequence

Take [2R5Z](https://files.rcsb.org/download/2R5Z.pdb) structure from PDB database and output only the protein sequence from there.

## For CSE students

### Fragment length frequency (1 mark) + rescaling (2 marks) 

You are given a file with each line indicating where a DNA fragment has mapped
on the chromosome. Your goal is to count individual fragment lengths, and then
normalize it by the total count of all fragment lengths. Once you have the
normalized count, you will plot that using plotting packages in Python. X-axis
will be fragment length (unit: base pairs) and Y-axis will be labelled
"Narmalized Frequency [A.U.]". Fragment length can simply be calculated by
subtracting 2nd column from the 3rd.

#### Rescaling

Often, you will received two sets of data with differnt emperical distribution.
The goal is to rescale one (query) to the other (reference). In this part, you
will write codes to achieve this. You are given a reference distribution (from
the 1st part above) and another file (query). You have to rescale (subsample
the data) so that when you draw the normalized frequency, it should almost
match the reference (almost because its emperical).

