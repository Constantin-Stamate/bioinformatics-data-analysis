# Bioinformatics Analysis

This repository contains tools and scripts for analyzing biological sequence data. It includes workflows for genomic and metagenomic data processing, taxonomic profiling, transcriptomic experiments, and regular-expression-based feature extraction, aimed at supporting bioinformatics research and applications.

---

## Genomic Analysis

This genomic analysis involves a series of bioinformatics steps to process and assess the quality of sequencing data:

- **Data Download & Decompression**: Raw genomic data files (in FASTA or FASTQ format) are downloaded and decompressed to obtain readable sequences.
- **Subsampling**: Subsets of these sequences are extracted using commands such as `head` to reduce computational overhead during testing.
- **Indexing**: The reference genome is indexed using the [Burrows-Wheeler Aligner (BWA)](http://bio-bwa.sourceforge.net/), allowing for rapid and accurate alignment.
- **Alignment**: Sequencing reads are aligned to the indexed reference genome using the BWA-MEM algorithm, producing alignment files in SAM format.
- **Quality Control**: [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) is used to generate detailed quality reports, including sequence length distribution, GC content, and per-base quality metrics.

---

## Metagenomic Analysis

This metagenomic analysis workflow focuses on profiling microbial communities from sequencing data:

- **Input Handling**: Raw reads in FASTQ format are preprocessed and optionally subsampled.
- **Environment Setup**: A Conda environment is prepared using [micromamba](https://mamba.readthedocs.io/en/latest/user_guide/micromamba.html), ensuring reproducibility and dependency management.
- **Taxonomic Profiling**: [MetaPhlAn](https://github.com/biobakery/MetaPhlAn) is used to detect clade-specific marker genes and estimate microbial abundances.
- **Database Management**: MetaPhlAn automatically downloads and verifies required reference databases.
- **Output & Visualization**: The resulting taxonomic profiles are parsed and visualized using bar plots that reflect relative microbial abundance.

This approach enables efficient and accurate characterization of complex microbial populations from environmental or host-associated samples.

---

## Transcriptomic Profiling in *C. elegans*

This RNA-Seq analysis focuses on the transcriptional comparison between *C. elegans* camt-1 mutants and wild-type neuronal cells:

- **Sample Preparation**: Specific neuronal classes were GFP-labeled, and worms were dissociated using both mechanical and enzymatic methods.
- **Cell Sorting**: GFP-positive cells were isolated using fluorescence-activated cell sorting (FACS) for RNA extraction.
- **Library Construction**: Low-input RNA libraries were prepared using the [NEBNext® Single Cell/Low Input RNA Library Prep Kit](https://www.neb.com/products/e6420-nebnext-single-cell-low-input-rna-library-prep-kit-for-illumina).
- **Sequencing**: The libraries were sequenced using [Illumina HiSeq 4000](https://www.illumina.com/systems/sequencing-platforms/hiseq-4000.html), generating single-end RNA-Seq reads.
- **Comparative Analysis**: Expression profiles between mutant and control samples were analyzed to detect differential expression across neuronal subtypes.

This workflow supports the study of gene regulation in specific neuronal populations and helps reveal transcriptional changes due to genetic mutations.

---

## Unix-based Genomic Feature Extraction

This pipeline showcases how Unix shell tools can be used to manipulate large-scale genomic annotation data:

- **Data Acquisition**: Compressed genomic annotation files are downloaded from public databases such as [Ensembl](https://www.ensembl.org/info/data/ftp/index.html) or [NCBI FTP](https://ftp.ncbi.nlm.nih.gov/genomes/).
- **Decompression**: Files are extracted using commands like `tar`, `bz2`, or `gzip` depending on their format.
- **Pattern Matching**: Tools like [`grep`](https://www.gnu.org/software/grep/), [`awk`](https://www.gnu.org/software/gawk/), and [`sed`](https://www.gnu.org/software/sed/manual/sed.html) are used to isolate lines containing relevant genomic features or annotations.
- **Data Filtering**: Regular expressions help extract or transform information such as gene names, coordinates, or coding regions.
- **Automation**: The process is scripted for reproducibility and efficiency, supporting fast preprocessing of large datasets.

This approach is ideal for high-throughput filtering, conversion, and extraction of genomic data prior to in-depth analysis or visualization.

---

## Author

This analysis was developed as part of the **Bioinformatics Bootcamp** organized at **UTM (Technical University of Moldova)**.

- GitHub: [Constantin-Stamate](https://github.com/Constantin-Stamate)
- Email: constantinstamate.r@gmail.com