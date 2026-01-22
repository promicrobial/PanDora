# PanDora: Pangenome Database of Reference Assemblies

A non-redundant human pangenome database for microbiome sequence decontamination using reference assemblies.

This database integrates genomes from the following projects:

- The Genome Reference Consortium human reference assembly, GRCh38 (NCBI RefSeq GCF_000001405.40)
- The T2T Consortium human reference assembly, CHM13v2.0 (NCBI RefSeq: GCF_009914755.1)
- The Human Pangenome Reference Consortium (HPRC) Year 1 assemblies (available on GitHub or NCBI; PRJNA730823)

## Contents

- Number of assemblies used: 94
- Total size: 9.2 GB
- File format: FASTQ

## To recreate the database

### Requirements

The following tools must be installed and available in your `PATH`:

- `minimap2`
- `samtools`
- `datasets` (NCBI datasets CLI)
- `biopet-validatefastq`
- `gunzip`
- `wget`
- `unzip`
- `panSieve` (https://github.com/cpnh/panSieve)

```bash
# Install dependencies using conda
conda env create -f environment.yml

# Clone panSieve and add to your PATH
git clone https://github.com/cpnh/panSieve

export PATH="panSieve/src/sieve:$PATH"
```

## Usage

```
bash create-pandora
```

## Documentation

Full documentation is available in the [docs](docs/) directory.

## License

MIT
