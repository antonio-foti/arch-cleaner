# Arch-Cleaner

A bash script to perform routine maintenance and cleanup tasks on Arch Linux systems.

## Features

- System updates (standard and aggressive options)
- Removal of orphaned packages
- Pacman cache cleaning
- Journal log cleaning
- Temporary file removal
- User cache cleaning

## Requirements

- Arch Linux or Arch-based distribution
- Bash shell
- Root privileges

## Installation (Linux)
```bash
git clone https://github.com/antonio-foti/arch-cleaner.git
cd arch-cleaner
chmod +x arch-cleaner
sudo cp arch-clenear /usr/local/bin/
```

## Uninstallation (Linux)
```bash
sudo rm /usr/local/bin/arch-cleaner
```

## Usage
```bash
arch-cleaner
```
   
## What the Script Does

### Standard Operations:

- Updates all packages (pacman -Syyu)
- Removes orphaned packages
- Cleans package cache (pacman -Scc)
- Removes unused packages
- Cleans systemd journal logs (keeping last 50MB)
- Removes temporary files
- Cleans user cache directories

 ## Safety Notes

1. The script requires root privileges and should be used with care
2. Always review the script before running
3. Consider backing up important data before system maintenance
4. Some operations (particularly the optional ones) are potentially destructive


## Contribution

Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

## License

MIT License - Free to use and modify
Created by Antonio Foti
