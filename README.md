# Variant Calling Workflow

This repository contains commands practiced during a bioinformatics practical
for a basic variant-calling workflow using BWA, SAMtools and BCFtools.

## Tools Used

- BWA
- SAMtools
- BCFtools
- Conda
- Linux/WSL

## 1. Setting up Conda channels

```bash
conda config --add channels bioconda
conda config --add channels conda-forge
conda config --add channels defaults
```

To check the configured channels:

```bash
conda config --show channels
```

## 2. Installing BWA
```bash
conda create -n bwa
conda activate bwa
conda install bwa
```

