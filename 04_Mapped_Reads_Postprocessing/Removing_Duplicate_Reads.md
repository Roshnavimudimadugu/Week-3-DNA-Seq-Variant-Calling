# Removing Duplicate Reads

## Objective

After filtering the mapped reads, duplicate reads were removed from the BAM files before variant calling.

Duplicate reads can arise during library preparation and sequencing, particularly because of PCR amplification. Multiple reads may therefore originate from the same original DNA fragment.

Removing duplicates helps reduce the possibility of artificially increased read support for a variant.

---

## Why Remove Duplicate Reads?

During PCR amplification, the same DNA fragment can be amplified multiple times.

These PCR duplicates can appear as multiple sequencing reads with identical or very similar alignment positions.

If duplicates are retained, they may:

- Artificially increase sequencing coverage
- Give excessive support to a particular allele
- Potentially affect variant calling

Therefore, duplicate reads were removed before proceeding to variant calling.

---

## Tool Used

**RmDup**

The Galaxy tutorial used the duplicate removal tool to process the filtered BAM files.

---

## Input Data

The input datasets were the filtered BAM files produced during the previous step:

- Filtered reads — Father
- Filtered reads — Mother
- Filtered reads — Proband

The three datasets were processed separately to generate duplicate-removed BAM files for each family member.

---

## Duplicate Removal Process

For each family member:

```text
Filtered BAM file
        │
        ▼
      RmDup
        │
        ▼
Duplicate-removed BAM file
