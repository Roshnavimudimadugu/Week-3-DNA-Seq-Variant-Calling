# VCF Inspection

## File Inspected

The final processed Variant Call Format (VCF) file generated during the variant calling workflow was inspected using Galaxy.

The inspected dataset was:

**bcftools norm on dataset 30**

The file contained variant calls mapped against the **hg19 reference genome**.

---

## Purpose of VCF Inspection

The purpose of inspecting the VCF file was to understand how variant information is organised and to identify individual variants for downstream interpretation.

---

## VCF Structure

The VCF file contains the following important columns:

| Column | Description |
|---|---|
| CHROM | Chromosome where the variant is located |
| POS | Genomic position of the variant |
| ID | Variant identifier |
| REF | Reference allele |
| ALT | Alternative allele |
| QUAL | Quality score associated with the variant call |
| FILTER | Indicates whether the variant passed filtering criteria |
| INFO | Additional information about the variant |

---

## Example Variant Observed

One of the variants observed in the VCF file was:

| CHROM | POS | REF | ALT |
|---|---:|---|---|
| chr1 | 762438 | T | G |

This indicates that at genomic position **762438 on chromosome 1**, the reference genome contains the allele **T**, while **G** was identified as an alternative allele in the analysed dataset.

---

## Conclusion

Inspection of the VCF file confirmed that the variant calling workflow successfully generated variant records containing genomic location, reference and alternative alleles, quality information, filtering information, and additional annotations. These variants will be further examined for biological and clinical interpretation.
