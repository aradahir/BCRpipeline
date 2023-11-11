# BCRpipeline

A pipeline for B cell receptor sequencing alignment and assembly.

# General info

This project is adapting the process from the immcantation framework (https://immcantation.readthedocs.io/en/stable/), mainly focus on the pre-processing, alignment, 
and assembly processes. The default input is illumina paired-end sequences that are sequenced from the constant region to variable region of BCR genes.

# Technologies
This project created with:

1. Python version >=3.6
2. Snakemake
3. pRESTO with these dependencies:
   setuptools 2.0
   NumPy 1.8
   SciPy 0.14
   pandas 0.24
   Biopython 1.77
   AlignSets requires MUSCLE v3.8
   ClusterSets requires USEARCH v7.0, vsearch v2.3.2, or CD-HIT v4.6.8
   AssemblePairs-reference requires USEARCH v7.0 or BLAST+ 2.5

# Requirement files
1. Primer
  1. forward primer (fasta)
  2. reverse primer (fasta)
2. Post-qc data folder where all data inside having this name format:
   {sampleID}_R{1,2}_trimmed.fastq.gz
   
# Run
 ```
Snakemake -j 1
 ```

# Output result
1. All step results, log files, and status text.
2. Filtered confident BCR segments with identities (fasta format).
3. Table of sequence quality.
   
# Warning
Config parameters could be adjusted via changing command in the snakefile. Defaults are illumina sequencing, nucleotide quality filter at 20, and mask primer length is 100.


