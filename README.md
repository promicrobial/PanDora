# PanDora: Pangenome Database of Reference Assemblies

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Conda](https://img.shields.io/badge/install%20with-conda-brightgreen.svg)](https://conda.io/)

> A non-redundant human pangenome database for microbiome sequence decontamination using reference assemblies.

## Overview

The `create-pandora` script constructs a non-redundant human pangenome database by combining standard reference genomes (GRCh38, CHM13-T2T) with Human Pangenome Reference Consortium (HPRC) graph-based sequences. The resulting database (PanDora) enables sensitive detection of human DNA contamination in sequencing datasets and provides a comprehensive reference for alignment-based analyses.


This database integrates genomes from the following projects:

- The Genome Reference Consortium human reference assembly, GRCh38 (NCBI RefSeq GCF_000001405.40)
- The T2T Consortium human reference assembly, CHM13v2.0 (NCBI RefSeq: GCF_009914755.1)
- The Human Pangenome Reference Consortium (HPRC) Year 1 assemblies (available on GitHub or NCBI; PRJNA730823)

## Quick Start

```bash
# Clone repository with dependencies
git clone --recursive https://github.com/promicrobial/pandora.git
cd pandora

# Install dependencies
conda env create -f environment.yml
conda activate pandora

# Create database (requires HPRC GFA file)
./create-pandora -g /path/to/hprc.gfa -o pandora_db -v
```

## Installation

### Requirements

The following tools must be installed and available in your `PATH`:

- bash (version 4+)
- Standard Unix tools (e.g. gunzip)
- `panSieve` ([GitHub](https://github.com/cpnh/panSieve)) 
- [seqtk](https://github.com/lh3/seqtk) v1.5
- [NCBI datasets CLI](https://github.com/ncbi/datasets) v18.15.0

```bash
# Install dependencies using conda
conda env create -f environment.yml

# Clone panSieve and add to your PATH
git clone https://github.com/cpnh/panSieve

export PATH="panSieve/src/:$PATH"
```

## Usage

### To recreate the database

```bash
create-pandora -g ref/hprc-v1.0-minigraph-grch38.gfa
```

### Command Line Options

| Option | Description | Default |
|--------|-------------|---------|
| `-g, --gfa FILE` | **Required**: Path to HPRC GFA file | - |
| `-o, --output DIR` | Output directory | `./pandora_output` |
| `-t, --threads NUM` | Number of threads | `4` |
| `-f, --force` | Force recreation of existing files | `false` |
| `-v, --verbose` | Enable verbose logging | `false` |
| `-k, --keep-temp` | Keep temporary files | `false` |
| `-d, --dry-run` | Show commands without executing | `false` |
| `-h, --help` | Show help message | - |
| `--version` | Show version information | - |

### Input Requirements

#### HPRC GFA File

Download from the [Human Pangenome Reference Consortium](https://humanpangenome.org):

```bash
# Example: Download and unzip HPRC GFA file
wget -q -O- ftp://ftp.sra.ebi.ac.uk/vol1/analysis/ERZ127/ERZ12792760/hprc-v1.0-minigraph-grch38.gfa.gz | gzip -d > hprc-v1.0-minigraph-grch38.gfa

```

## Documentation

Full documentation is available in the [docs](docs/) directory.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
