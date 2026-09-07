# Variant Calling

This section documents the variant calling stage of the Exome Sequencing Data Analysis workflow.

After mapped reads were filtered and duplicate reads were removed, the processed BAM files from the father, mother, and proband were used for variant calling.

This stage includes:

1. Generating variant calls using FreeBayes
2. Post-processing the FreeBayes variant calls

The aim of this stage was to identify genetic variants across the family trio for subsequent annotation and candidate variant analysis.
