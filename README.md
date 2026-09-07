# Week 3: DNA-Seq Variant Calling and VCF Interpretation

## Exome Sequencing Analysis for Identifying Candidate Disease-Causing Variants

---

## Project Overview

This repository documents my Week 3 practical learning in **DNA sequencing analysis, variant calling, and Variant Call Format (VCF) interpretation**.

The practical analysis was completed using the **Galaxy Training Network (GTN) tutorial: Exome sequencing data analysis for diagnosing a genetic disease**.

The project follows a family-based whole-exome sequencing workflow, starting with raw sequencing reads and progressing through quality control, read mapping, variant calling, functional annotation, and candidate variant detection.

The main aim is to understand how raw sequencing data can be transformed into biologically meaningful information and used to identify potential genetic variants associated with a disease phenotype.

---

## Biological Background

The analysis investigates whole-exome sequencing data from a **family trio**.

The family consists of:

- **Father:** Unaffected
- **Mother:** Unaffected
- **Proband:** Affected boy child

The affected child has **osteopetrosis**, while both parents are unaffected. The parents are also described in the tutorial as **consanguineous**.

The objective of this analysis is to identify genetic variation that could potentially explain the disease phenotype observed in the affected child.

### Family Structure

```text
             Father ───────── Mother
            Unaffected        Unaffected
                  \            /
                   \          /
                    Proband
                 Affected child
                 Osteopetrosis
