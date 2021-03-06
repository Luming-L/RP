Find Individual Motif Occurrences
# Knowledge
A motif is a sequence pattern that occurs repeatedly in a group of related sequences.
Motifs can be represented as position-dependent letter-probability matrices that describe the probability of each possible letter at each position in the pattern.
A text file in MEME minimal motif format can contain more than one motif, and also (optionally) specifies the 
# Options
`--o` or --oc
`--parse-genomic--coord`
`--thresh`
`--max-stored-scores`
--max-stored-scores <int> (default=100000)

# Input
`motif file` Format:
- Version (required)
- Alphabet (recommended)
- Strands (optional)
- Background frequencies (recommended)
- Motifs (required)
[The minimal MEME format-DNA](http://meme-suite.org/doc/examples/sample-dna-motif.meme)

`sequence file`
# Output
# Result
## ACC
79801 motif occurences with a p-value less than 0.0001
Each line stands for each significant match to a motif.
The lines are sorted in order of decreasing statistical significance (increasing _p_-value).
score
p-value
q-value: The _p_-values for each motif occurrence are converted to _q_-values following the method of Benjamini and Hochberg ("_q_-value" is defined as the minimal false discovery rate at which a given motif occurrence is deemed significant).

 ACC_peakCalls_fimo_out]$ ll
total 25600
-rw-r--r-- 1 s1949868 eddie_users 14674239 Jun  2 05:02 cisml.xml
-rw-r--r-- 1 s1949868 eddie_users  7172478 Jun  2 05:02 fimo.gff
-rw-r--r-- 1 s1949868 eddie_users   451659 Jun  2 05:02 fimo.html
-rw-r--r-- 1 s1949868 eddie_users  3598472 Jun  2 05:02 fimo.txt
-rw-r--r-- 1 s1949868 eddie_users     2550 Jun  2 05:02 fimo.xml

cd ACC_peak_fimo_out/
[s1949868@bioinfmsc3 ACC_peak_fimo_out]$ ll
total 44596
-rw-------. 1 s1949868 s1949868 22396716 Jun  6 01:39 cisml.xml
-rw-------. 1 s1949868 s1949868 16207458 Jun  6 01:40 fimo.gff
-rw-------. 1 s1949868 s1949868   500671 Jun  6 01:40 fimo.html
-rw-------. 1 s1949868 s1949868  6551092 Jun  6 01:39 fimo.tsv
-rw-------. 1 s1949868 s1949868     2585 Jun  6 01:39 fimo.xml


```bash
wc -l ./Fimo/*_peakCalls_fimo_out/fimo.gff
```
    49421 ./Fimo/ACC_peakCalls_fimo_out/fimo.gff
    75487 ./Fimo/BLCA_peakCalls_fimo_out/fimo.gff
    97028 ./Fimo/BRCA_peakCalls_fimo_out/fimo.gff
    84528 ./Fimo/CESC_peakCalls_fimo_out/fimo.gff
    98454 ./Fimo/CHOL_peakCalls_fimo_out/fimo.gff
    58905 ./Fimo/COAD_peakCalls_fimo_out/fimo.gff
    61201 ./Fimo/ESCA_peakCalls_fimo_out/fimo.gff
    50720 ./Fimo/GBM_peakCalls_fimo_out/fimo.gff
    51725 ./Fimo/HNSC_peakCalls_fimo_out/fimo.gff
    55350 ./Fimo/KIRC_peakCalls_fimo_out/fimo.gff
    64279 ./Fimo/KIRP_peakCalls_fimo_out/fimo.gff
    52792 ./Fimo/LGG_peakCalls_fimo_out/fimo.gff
    53374 ./Fimo/LIHC_peakCalls_fimo_out/fimo.gff
    60527 ./Fimo/LUAD_peakCalls_fimo_out/fimo.gff
    56481 ./Fimo/LUSC_peakCalls_fimo_out/fimo.gff
    96894 ./Fimo/MESO_peakCalls_fimo_out/fimo.gff
    53490 ./Fimo/PCPG_peakCalls_fimo_out/fimo.gff
    71332 ./Fimo/PRAD_peakCalls_fimo_out/fimo.gff
    49270 ./Fimo/SKCM_peakCalls_fimo_out/fimo.gff
    58766 ./Fimo/STAD_peakCalls_fimo_out/fimo.gff
    54451 ./Fimo/TGCT_peakCalls_fimo_out/fimo.gff
    48814 ./Fimo/THCA_peakCalls_fimo_out/fimo.gff
    54759 ./Fimo/UCEC_peakCalls_fimo_out/fimo.gff

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzNjU0NjgxMjMsMTY4NzYwMjAwNSwxMj
U5NzU0NywxMzk0Nzk1MDM2LC04MzUzNDM5MTksNTEwNzkyMDI3
LDEwMzU0ODYzMTksMTY5NzQwOTk5NiwxOTY2NjEyNDUyLDQ0Mj
Q2MzU2NCwtMTM2NDQ3OTA2MywtMTE1NDU2OTczNiwtMTUxMjI5
MDUyOCwtMTMyNDE0NjkxMSw3MzQ1MTE1NjksMTYwNzY5NjY3LD
Q3NTQyNjU0NSwxNDkyNTE5MzE5LDExNzc5MDA4MTMsNDA4MDM5
MTA0XX0=
-->