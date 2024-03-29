### Note: This repository has been archived and consolidated into: https://github.com/pepkit/pep-pipelines/

# pep-snakemake

Example simple and bioinformatic pipelines using PEPs and Snakemake.

## Simple pipeline

Here, we're counting lines using `wc`.

```
cd simple/pipelines
snakemake --cores 1
```

## Bioinformatics pipeline

Here, we're aligning fastq files using `bowtie2`.

### 1. Install and configure required software

Install: 
- Bowtie2 aligner
- refgenie Python package (manages Bowtie2 index)

Configure:
- initialize refgenie config (`refgenie init -c path.yml`)
- set `REFGENIE` environment variable to point to the initialized config
- obtain `hg38/bowtie2_index` asset (either `refgenie build ...` or `refgenie pull ...`)

### 2. Run the pipeline

```
cd bioinformatic/pipelines
snakemake --cores 4
```
