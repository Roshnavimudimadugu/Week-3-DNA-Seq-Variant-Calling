# Read Mapping

## Objective

The purpose of read mapping was to align the raw sequencing reads from each member of the family trio to the human reference genome.

After quality control confirmed that the sequencing reads were suitable for further analysis, the reads from the father, mother, and proband were mapped separately.

The output of this step was one mapped BAM file for each family member.

---

## Tool Used

**Map with BWA-MEM**

BWA-MEM is a read alignment tool used to map sequencing reads to a reference genome.

For this analysis, the reads were mapped to:

**Human: hg19**

---

## Reference Genome

The reference genome selected for mapping was:

**Human Feb. 2009 (GRCh37/hg19)**

The Galaxy server provided a built-in genome index for hg19.

---

## Input Data

The analysis used paired-end sequencing reads from three individuals:

| Sample | Forward Reads | Reverse Reads |
|---|---|---|
| Father | `father_R1.fq.gz` | `father_R2.fq.gz` |
| Mother | `mother_R1.fq.gz` | `mother_R2.fq.gz` |
| Proband | `proband_R1.fq.gz` | `proband_R2.fq.gz` |

---

# Mapping the Father Sample

The father sequencing reads were mapped using **Map with BWA-MEM**.

### Parameters

- **Reference genome source:** Use a built-in genome index
- **Reference genome:** Human: hg19
- **Read type:** Paired-end

### Input Reads

- First set of reads: `father_R1.fq.gz`
- Second set of reads: `father_R2.fq.gz`

### Read Group Information

Read group information was specified as:

- **Read group identifier (ID):** `000`
- **Read group sample name (SM):** `father`

---

# Mapping the Mother Sample

The mother sequencing reads were mapped using the same procedure.

### Input Reads

- First set of reads: `mother_R1.fq.gz`
- Second set of reads: `mother_R2.fq.gz`

### Read Group Information

- **Read group identifier (ID):** `001`
- **Read group sample name (SM):** `mother`

---

# Mapping the Proband Sample

The sequencing reads from the affected child were mapped using the same procedure.

### Input Reads

- First set of reads: `proband_R1.fq.gz`
- Second set of reads: `proband_R2.fq.gz`

### Read Group Information

- **Read group identifier (ID):** `002`
- **Read group sample name (SM):** `proband`

---

## Why Are Read Groups Important?

Read group information was added during mapping to identify the sequencing data and biological sample.

### Read Group Identifier (ID)

The ID identifies the sequencing run.

Each sample was assigned a unique identifier:

- Father: `000`
- Mother: `001`
- Proband: `002`

Unique IDs are important because duplicate read group identifiers can cause problems during downstream multisample analysis.

### Sample Name (SM)

The sample name identifies the biological sample.

The sample names used were:

- `father`
- `mother`
- `proband`

These sample names are important for downstream tools, including variant calling and GEMINI, where individual samples need to be identified in a multisample analysis.

---

## Output

The read mapping step produced three mapped read datasets in BAM format:

- Mapped reads for the father
- Mapped reads for the mother
- Mapped reads for the proband

These BAM files contained sequencing reads aligned to the hg19 human reference genome.

---

## Workflow Position

```text
Paired-End FASTQ Files
        │
        ▼
   BWA-MEM Mapping
        │
        ▼
Reference Genome: hg19
        │
        ▼
Mapped BAM Files
        │
        ▼
Mapped Reads Post-processing
