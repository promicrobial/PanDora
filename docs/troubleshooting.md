# Troubleshooting

### Common Issues

#### Permission Denied Error

```bash
# Make script executable
chmod +x create-pandora
```

#### Missing Dependencies

```bash
# Check which tools are missing
which datasets seqtk wget unzip

# Install missing tools using conda
conda install -c bioconda seqtk
conda install -c conda-forge wget
```

#### Memory Issues
```bash
# Reduce thread count for systems with limited RAM
./create-pandora -g input.gfa -t 2 -o output/
```

### Getting Help

#### Check Log Files

```bash
# View detailed logs
tail -f pandora_output/logs/pandora_summary.txt
```

#### Enable Verbose Mode

```bash
# Run with verbose output for debugging
./create-pandora -g input.gfa -v -k -o output/
```

#### Report Issues

If you encounter persistent issues:

1. Check the [GitHub Issues](https://github.com/cpnh/pandora/issues)
2. Provide system information
3. Include relevant log files and error messages