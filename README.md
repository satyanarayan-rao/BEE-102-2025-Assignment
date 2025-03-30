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

### Multi-line sequence fasta to single-line fasta file (1)

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

### Building Markov transition matrix (2)

You have learned important differences between simple dinucleotide frequency
model and Markov models. Your goal is to build one from the input sequence. In
the Jupyter notebook, you should print the transition matrix. 

## For CSE students

