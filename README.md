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

## 3. Installing SAMtools and BCFtools

```bash
conda create -n variantcall -c conda-forge -c bioconda samtools bcftools
conda activate variantcall
```

## 4. Reference Genome Indexing

```bash
bwa index reference.fasta
```

## 5. Read Mapping

``` bash

bwa mem reference.fasta Sample1.fastq.gz Sample2.fastq.gz > aligned.sam
```

## 6. SAM to BAM Conversion

```bash
samtools view -h -S -b aligned.sam -o aligned.bam
```

## 7. BAM Sorting

```bash
samtools sort aligned.bam -o sorted.bam
```
## 8. BAM Indexing

```bash
samtools index sorted.bam
```

## 9. Variant Calling

```bash
bcftools mpileup -Ou -f reference.fna sorted.bam | bcftools call -mv -Ov -o variants.vcf
```
## 10. Workflow

FASTQ reads → BWA mapping → SAM → BAM → Sorted BAM → BAM indexing → Variant calling → VCF

## Note

This repository documents a basic variant-calling workflow practiced during a bioinformatics practical using Linux/WSL, Conda, BWA, SAMtools and BCFtools.
