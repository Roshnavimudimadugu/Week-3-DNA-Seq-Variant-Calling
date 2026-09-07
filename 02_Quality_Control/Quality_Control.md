# Quality Control

## Objective

The purpose of quality control (QC) is to assess the quality of the raw sequencing reads before proceeding with read mapping and variant calling.

Poor-quality bases, sequencing artefacts, adapter contamination, or unusual sequence composition can affect downstream alignment and variant identification. Therefore, the quality of the FASTQ files was evaluated before further analysis.

---

## Quality Control Tool

Quality control was performed using:

**FastQC**

The results from all family members were then summarised using:

**MultiQC**

The analysed samples were:

- Father
- Mother
- Proband (affected child)

Each individual had paired-end sequencing reads:

- Forward reads (R1)
- Reverse reads (R2)

---

## FastQC Analysis

FastQC was used to evaluate the quality of the raw sequencing reads.

The following quality metrics were examined:

- Per base sequence quality
- Per sequence quality scores
- Per base sequence content
- Per sequence GC content
- Adapter content
- Sequence length distribution
- Overrepresented sequences

FastQC generates graphical reports that help identify potential problems in sequencing data.

---

## MultiQC Summary

MultiQC was used to combine the FastQC results from all sequencing files into a single report.

This made it possible to compare the sequencing quality of:

- Father
- Mother
- Proband

The MultiQC report provides an overall summary of sequencing quality across all samples.

---

## Outcome

The quality control results were inspected before proceeding to read mapping.

The sequencing data passed through the quality assessment stage and were subsequently used for alignment against the reference genome.

The next stage of the workflow was read mapping using BWA-MEM.

---

## Workflow Position

```text
Raw FASTQ files
       ↓
FastQC
       ↓
MultiQC
       ↓
Quality assessment
       ↓
Read Mapping
