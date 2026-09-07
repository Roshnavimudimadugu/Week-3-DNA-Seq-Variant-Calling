# Candidate Variant Detection

## Objective

The final analysis step was to identify variants that could potentially explain the osteopetrosis phenotype of the affected boy (proband).

The family trio consisted of:

- Father — unaffected
- Mother — unaffected
- Proband — affected by osteopetrosis

The parents were consanguineous.

The genotype information, family relationships, and phenotype information stored in the GEMINI database were used to search for variants compatible with plausible inheritance patterns.

---

## Determining the Inheritance Pattern

Because the affected child had two unaffected parents, the observed phenotype was compatible with an inherited **autosomal recessive** disease model.

The tutorial also notes that other possibilities, such as de novo mutations, may be considered.

However, the main candidate variant search in this workflow focused on:

**Autosomal recessive inheritance**

---

## Tool Used

**GEMINI inheritance pattern**

This tool allows variants to be identified according to standard inheritance models without manually writing complex SQL queries.

The tool can search for variants compatible with inheritance patterns such as:

- Autosomal recessive
- Autosomal dominant
- X-linked recessive
- X-linked dominant
- Autosomal de novo
- X-linked de novo
- Compound heterozygous
- Loss of heterozygosity (LOH)

---

## Input Data

The input was:

**The GEMINI database generated in the previous step.**

The database contained:

- Variant information
- Genotype calls for the father
- Genotype calls for the mother
- Genotype calls for the proband
- Pedigree information
- Functional variant annotations

---

## Parameters Used

### GEMINI Database

The GEMINI database generated using **GEMINI load**.

### Assumption About the Inheritance Pattern

**Autosomal recessive**

### Additional Variant Constraints

The following constraint was applied:

```text
impact_severity != 'LOW'
