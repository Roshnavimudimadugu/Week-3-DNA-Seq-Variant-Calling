# Data Preparation

## Objective

The data preparation stage was performed to obtain and organise the datasets required for the Exome Sequencing Data Analysis workflow.

According to the Galaxy Training Network tutorial, this analysis investigates a family trio in which:

- **Father** – unaffected
- **Mother** – unaffected
- **Proband (boy child)** – affected by osteopetrosis

Both parents are described in the tutorial as consanguineous. The objective of the analysis is to identify the genetic variation responsible for the disease.

---

## Analysis Approach

The Galaxy tutorial provides two possible starting points:

1. Starting from original sequencing reads in FASTQ format and performing the complete analysis, including quality control and read mapping.
2. Starting from premapped reads in BAM format and proceeding directly to downstream processing.

For this workflow, I followed the **complete analysis starting from the original sequencing reads in FASTQ format**.

---

## Raw Sequencing Data

The original sequencing datasets were obtained from Zenodo and consisted of paired-end reads from the family trio.

### Father

- `father_R1.fq.gz`  
  https://zenodo.org/record/3243160/files/father_R1.fq.gz

- `father_R2.fq.gz`  
  https://zenodo.org/record/3243160/files/father_R2.fq.gz

### Mother

- `mother_R1.fq.gz`  
  https://zenodo.org/record/3243160/files/mother_R1.fq.gz

- `mother_R2.fq.gz`  
  https://zenodo.org/record/3243160/files/mother_R2.fq.gz

### Proband (Affected Child)

- `proband_R1.fq.gz`  
  https://zenodo.org/record/3243160/files/proband_R1.fq.gz

- `proband_R2.fq.gz`  
  https://zenodo.org/record/3243160/files/proband_R2.fq.gz

A total of **six FASTQ datasets** were used in the analysis.

---

## Importing the Data into Galaxy

The six sequencing datasets were imported into Galaxy using the **Upload** tool and the **Paste/Fetch Data** option.

The datatype for all sequencing files was set to:

`fastqsanger.gz`

After uploading, the datasets were checked to ensure that the correct datatype had been assigned.

---

## Dataset Organisation

The datasets were renamed using their corresponding file names to make the analysis easier to follow.

The datasets were then labelled using Galaxy name tags:

- `#father`
- `#mother`
- `#child`

These tags helped track the datasets belonging to each family member throughout the workflow.

Galaxy propagates name tags beginning with `#` to datasets generated from the tagged input datasets. Therefore, the tags made it easier to follow the father, mother, and child datasets throughout the downstream analysis.

---

## Reference Genome

The analysis used the human reference genome:

**Human Feb. 2009 (GRCh37/hg19)**

The Galaxy tutorial provides the following hg19 chromosome 8 reference sequence:

`https://zenodo.org/record/3243160/files/hg19_chr8.fa.gz`

This reference sequence was used for the downstream read mapping and variant analysis workflow.

---

## Output of Data Preparation

At the end of the data preparation stage, the following were available for downstream analysis:

- Six paired-end FASTQ datasets from the family trio
- Correct FASTQ datatype assignment (`fastqsanger.gz`)
- Dataset names organised by family member
- Galaxy name tags for father, mother, and child
- Human reference genome information (`hg19`)

The prepared datasets were then used for the subsequent stages:

1. Quality Control
2. Read Mapping
3. Mapped Reads Post-processing
4. Variant Calling
5. Variant Annotation and Reporting
6. Candidate Variant Detection

---

## Tutorial Reference

Galaxy Training Network. **Exome Sequencing Data Analysis for Diagnosing a Genetic Disease**.

https://training.galaxyproject.org/training-material/topics/variant-analysis/tutorials/exome-seq/tutorial.html#data-preparation
