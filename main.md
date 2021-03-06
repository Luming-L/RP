Data:
404 donors
410 samples
796 replicates = 386 technical replicate pairs (772) + 24 single replicate samples 

Donor – An individual person. Multiple tumor samples can come from a single donor.
Sample – A piece of tumor tissue. Multiple technical replicates can exist per sample.
Technical Replicate – Tumor tissue was homogenized prior to ATAC-seq into a nuclei suspension. Each technical replicate represents an individual ATAC-seq reaction performed in a separate tube on different nuclei isolated from the same sample.

counts matrix
raw and normalized counts
The normalized peak score of the given peak (i.e. "score-per-million")
To do this, the MACS2 peak scores (-log10(p-value)) for each sample were converted to a “score per million” by dividing each individual peak score by the sum of all of the peak scores in the given sample divided by 1 million. 
MACS2 output files:
The score (5th) column contains 10 times of the average score in the broad region
5th: integer score for display. It's calculated as `int(-10*log10pvalue)` or `int(-10*log10qvalue)` depending on whether `-p` (pvalue) or `-q` (qvalue) is used as score cutoff.

## Normalised read count matrix

A data table that is obtained after  [normalisation](https://www.ebi.ac.uk/training/online/glossary/normalisation)  of next-generation sequencing data. It usually organises the samples in columns and genes/genomic loci in rows. The values represent the summarised read counts per genomic region (e.g. gene, transcript) after normalisation (e.g.  [RPKM](https://www.ebi.ac.uk/training/online/glossary/rpkm)  values).

# why read counts matrix
ATAC-seq can be used to compare chromatin accessibility between two cellular conditions.
The normalization method will affect the result of differential analysis.
ATAC-seq users should be aware of the interpretations of potential bias within experimental data and the assumptions of the normalization method implemented.

constructs a consensus read count matrix from _MACS2_ replicate peak sets of _m_ query regions by _n_ samples.
The whole workflow for differential accessiblity
MACS2:
1. _MACS2_ constructs an ATAC fragment pileup from aligned paired-end data
2. builds a local bias track through a series of parameters to estimate background noise
3. finally compares ATAC signal to the local background at each genomic bp using a Poisson test.
4. Significant nearby regions are then merged into a peak.
DiffBind:
5. calculate the total number of reads in queried peak regions, which should eliminate global differences in favor of reducing any technical biases.
DESeq2:
6. The count matrix with normalization factors is then subject to the _DESeq2_ framework of dispersion estimation and negative binomial generalized linear model (GLM) fitting for hypothesis testing, according to the design matrix.
7. follow a _voom_ transformation to log2 counts per million (log2CPM) 
8. further quantile normalized in _VIII_
9. The log2CPM transformation simply scales by full library size and maintains those assumptions, while quantile normalization equalizes the signal distribution across all libraries

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIzMTgwMjA2MiwzMzE3OTE0NDAsLTIwOT
k0MzM1MzQsLTE3ODE2MDkwOTksLTIxMzQ2NDUzOTUsMTk2ODM4
OTc4NCw3MjAyOTA3ODYsLTEyMTEwOTYyNCwtMTgwMTk1MzEwNy
wxNjU5MzY4OTI1LC0xNDM2MjM3NzI0LDIxMDA5OTI3MSwzNDI0
Mzg2NDAsLTIwNzQ3MDgyMDEsLTE2NTc5MTg4NTgsLTU1NjM5Nz
k3MiwtMTQ4MjU1NjgwNCwtOTYyMTQ0MzcyLDEyMjY5MzQxMzAs
LTE2MTUyNzg4MDRdfQ==
-->