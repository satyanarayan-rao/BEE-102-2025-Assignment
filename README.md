# BEE-102-2025-Assignment

This repository has programming question for CSE 2<sup>nd</sup> year students
(2023 admission), and CY 1<sup>st</sup> year students (2024 admission).

Few notes for completing the assignment:

1. All codes are to be written in Jupyter-Notebook (.ipynb file). 

2. Notebook file should clealy state question number and good documentation. 

3. Only notebooks uploaded on Github will be graded. 


## For CY students

### Normalized fragment length frequency (2 marks)

You are given a file with each line indicating where a DNA fragment has mapped
on the chromosome. Your goal is to count individual fragment lengths, and then
normalize it by the total count of all fragment lengths. Once you have the
normalized count, you will plot that using plotting packages in Python. X-axis
will be fragment length (unit: base pairs) and Y-axis will be labelled
"Narmalized Frequency [A.U.]". Fragment length can simply be calculated by
subtracting 2nd column from the 3rd.

[query.bed.gz](https://figshare.com/ndownloader/files/53306780?private_link=727f8d920a1b8415f09a) 

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

[data](https://figshare.com/ndownloader/files/49307590)

Example lines from the above file: 

```
2	chr1	90919	91937	chr1:91382-91550|carroll_ctcf_mcf7_v45m`2_GTGGCACCAGGTGGCAGCA	16.2951	+	chr1	90838	91006	IH02_00.pairs@15152	168	+
2	chr1	90919	91937	chr1:91382-91550|carroll_ctcf_mcf7_v45m`2_GTGGCACCAGGTGGCAGCA	16.2951	+	chr1	90846	90998	IH02_04.pairs@4163	152	+
2	chr1	90919	91937	chr1:91382-91550|carroll_ctcf_mcf7_v45m`2_GTGGCACCAGGTGGCAGCA	16.2951	+	chr1	90851	91000	IH02_04.pairs@4164	149	+
```

From every line of this file, you have to derive three values:

- X: Difference between two centers. C1 = center using Column3 and Column4, C2 = center using Column9 and Column10. X-coordinate will be C2 - C1 

- Y: Column10 - Column9 

- Z: Counter of Y at X. By default Z for Y at X is Zero. 

And example is:

-500 65 10

X: -500, Y: 65, and Z: 10, telling that 500 bases relative to protein bound to DNA has 10 fragments of 65 base pair in size.

You have to plot a heatmap of this.  

### Writing codes for linear regression (2 marks)

Design data yourself, 

### Reading a PDB file to output protein sequence

Take [2R5Z](https://files.rcsb.org/download/2R5Z.pdb) structure from PDB database and output only the protein sequence from there.

## For CSE students

### Fragment length frequency (1 mark) + rescaling (2 marks) 

You are given a file (see link below) with each line indicating where a DNA fragment has mapped
on the chromosome. Your goal is to count individual fragment lengths, and then
normalize it by the total count of all fragment lengths. Once you have the
normalized count, you will plot that using plotting packages in Python. X-axis
will be fragment length (unit: base pairs) and Y-axis will be labelled
"Narmalized Frequency [A.U.]". Fragment length can simply be calculated by
subtracting 2nd column from the 3rd.

[query.bed.gz](https://figshare.com/ndownloader/files/53306780?private_link=727f8d920a1b8415f09a) 

#### Rescaling

Often, you will received two sets of data with differnt emperical distribution.
The goal is to rescale one (query) to the other (reference). In this part, you
will write codes to achieve this. You are given a reference distribution
(`reference.hist`) and a query bed file (query.bed.gz). You have to rescale
(subsample the data) so that when you draw the normalized frequency, it should
almost match the reference. 

[reference.hist](https://figshare.com/ndownloader/files/53306810?private_link=727f8d920a1b8415f09a)

### Building Markov transition matrix (1 mark)

Same as asked to CY students (see above)

### Multi-line sequence fasta to single-line fasta file (1 mark)

Same as asked to CY students (see above)

### Writing Viterbi Algorithm for the Primer (3 marks) 

Write the Viterbi algorithm to implment Nature Primer.

Here are some suggestions:

a. You can begin by first defining all the parameters, such as states, transition matrix, and emmision matrix etc.

b. You can write a function to exactly calculate the values mentioned in the primer, for example, you can define a function `get_log_prob_of_a_given_path ("EEEEEEEEEEEEEEEEEE5IIIIIII", "CTTCATGTGAAAGCAGACGTAAGTCA")`. This should output `-41.22`. 

By doing the above two, you earn `1` mark. 

Now, you have to implement this in real to get max likely path that would emmit the observed sequence. You MUST note that  maximum likely path will just be `Es`, but that is okay. Implementation is the key. 

### V-plot (1 mark)

Same as asked to CY students 

[data](https://figshare.com/ndownloader/files/49307590)

### Principle Component Analysis (2 marks)

Write codes in Python to perform PCA and understand why we need such
unsupervised learning method. 
