# Linux `shred` Command - Secure File Deletion

## 📌 Overview
The `shred` command overwrites files multiple times with random data before optionally deleting them, making recovery extremely difficult.

## ⚠️ Important Warnings
- **SSDs/Flash Storage**: May not be effective due to wear leveling
- **Journaling Filesystems**: Some data may remain in journal
- **Backups/RAID**: Copies may exist elsewhere
- **Not for Directories**: Use on files only

## 📖 Basic Syntax
```bash
shred [OPTIONS] FILE...
```

## 🎯 Common Options
| Option | Description |
|--------|-------------|
| `-f, --force` | Force permissions to allow writing |
| `-u, --remove` | Truncate and remove after overwriting |
| `-v, --verbose` | Show progress |
| `-n, --iterations=N` | Overwrite N times (default: 3) |
| `-z, --zero` | Final overwrite with zeros to hide shredding |
| `-s, --size=N` | Shred only N bytes (suffixes: K,M,G,T,P) |

## 🚀 Practical Examples

### Basic Secure Delete
```bash
shred -u sensitive_file.txt
```

### Verbose with Multiple Passes
```bash
shred -v -n 7 -u file_to_destroy
```

### Shred & Hide Activity
```bash
shred -z -u file  # Final zero pass to hide shredding
```

### Force Shred Read-only File
```bash
shred -f -u protected_file.conf
```

### Shred Specific Size Only
```bash
shred -s 1M -u large_file.bin  # Shred only first 1MB
```

### Multiple Files
```bash
shred -u file1.txt file2.txt file3.log
```

## 🔧 Advanced Usage

### Overwrite Entire Disk/Partition
```bash
shred -v -n 3 /dev/sdX  # CAREFUL: This destroys ALL data!
```

### Using Random Data Source
```bash
shred --random-source=/dev/urandom -u file
```

### Remove without Truncating
```bash
shred --remove=wipe file  # Only on supported filesystems
```

## 📝 Notes
- Default is 3 passes (US DoD 5220.22-M compliant)
- Use `shred --help` for all options
- Consider alternatives for modern hardware:
  - `secure-delete` package tools
  - `dd if=/dev/urandom of=file`
  - Physical destruction for maximum security

## 🔗 Related Commands
- `rm` - Standard file removal
- `wipe` - Alternative secure delete tool
- `dd` - Low-level data manipulation
- `srm` - Secure rm from `secure-delete` package
