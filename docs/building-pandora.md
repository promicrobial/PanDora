# Installation

This guide will walk you through installing the dependencies to build PanDora from scratch.

## Software Dependencies

- Bash 4.0+
- Python 3.8+
- Conda or Miniconda

Clone the repository and install dependencies using either option below.

## Option 1: Using Conda (Recommended)

```bash
# Create and activate conda environment
conda env create -f environment.yml
conda activate pandora

# Verify installation
chmod +x ./create-pandora
./create-pandora --version
```

## Option 2: Manual Installation

If you prefer to install dependencies manually or encounter issues with the conda installation:

### NCBI Datasets

Download the latest version from NCBI [here](https://www.ncbi.nlm.nih.gov/datasets/docs/v2/command-line-tools/download-and-install/)

### SeqTk

```bash
# Install seqtk
git clone https://github.com/lh3/seqtk.git
cd seqtk
make
```

## Download panSieve

```bash
# Clone panSieve and add to your PATH
git clone https://github.com/cpnh/panSieve.git

export PATH="panSieve/src/:$PATH"
```

## Building PanDora

Make the main script executable

```bash
chmod +x create-pandora
```

The minimal command to run PanDora requires only an HPRC GFA file:

```bash
create-pandora -g ref/hprc-v1.0-minigraph-grch38.gfa
```

This will:

1. Download reference genomes (GRCh38, CHM13)
2. Process the HPRC GFA file with PanSieve
3. Combine everything into a non-redundant database
