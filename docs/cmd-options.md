# Command Line Options

## Required Parameters

| Option | Description | Example |
|--------|-------------|---------|
| `-g, --gfa FILE` | Path to GFA file for processing | `-g hprc-v1.0.gfa` |

## Optional Parameters

| Option | Description | Default | Example |
|--------|-------------|---------|---------|
| `-o, --output DIR` | Output directory | `./pandora_output` | `-o /data/pandora` |
| `-t, --threads NUM` | Number of threads | `4` | `-t 16` |
| `-f, --force` | Force redownload/recreation | `false` | `-f` |
| `-k, --keep-temp` | Keep temporary files | `false` | `-k` |
| `-v, --verbose` | Enable verbose output | `false` | `-v` |
| `-d, --dry-run` | Show commands without executing | `false` | `-d` |

## Help and Information

| Option | Description |
|--------|-------------|
| `-h, --help` | Display help message |
| `--version` | Display version information |