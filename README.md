# Arch-Cleaner

A bash script to perform routine maintenance and cleanup tasks on Arch Linux systems.

![usage](./usasge.gif)

## Features

- System updates (standard and aggressive options)
- Removal of orphaned & unused packages (with configurable aggressiveness)
- Pacman cache cleaning (configurable thoroughness)
- Journal log cleaning
- Temporary file removal (conditional on mode)
- User cache cleaning (configurable thoroughness)
- Optional trash emptying
- Optional post-cleanup reboot

## Requirements

- Arch Linux or Arch-based distribution
- Bash shell
- Root privileges
- Systemd (for journal log cleaning)

## Installation
```bash
git clone https://github.com/antonio-foti/arch-cleaner.git
cd arch-cleaner
chmod +x arch-cleaner
sudo cp arch-cleaner /usr/local/bin/
```

## Uninstallation
```bash
sudo rm /usr/local/bin/arch-cleaner
```

## Usage

```bash
sudo arch-cleaner [OPTIONS]
```
   
### Options:

- -t Empty trash for all users
- -r Reboot after cleanup
- -a Aggressive mode (force refresh databases, complete cache removal)


### Examples:

- Standard cleanup: sudo arch-cleaner
- Cleanup with trash emptying: sudo arch-cleaner -t
- Aggressive system refresh: sudo arch-cleaner -a
- Full cleanup with reboot: sudo arch-cleaner -tra


## What the Script Does

### Standard Operations:

- Updates all packages (pacman -Syu)
- Removes orphaned & unused packages (with confirmation)
- Cleans package cache (pacman -Sc)
- Cleans systemd journal logs (keeping last 50MB)
- Removes temporary files (only during reboot)
- Cleans user cache directories (preserves directory structure)


### Aggressive Mode (-a):

- Forces database refresh (pacman -Syyu)
- Removes ALL cached packages (pacman -Scc)
- More aggressive orphaned & unused package removal
- Deletes entire .cache directories
- Always removes temporary files (regardless of reboot status)


### Optional Operations:

- Trash emptying (-t flag) - removes files from all user trash directories
- System reboot (-r flag) - reboots after completion


## Safety Notes

- The script requires root privileges and should be used with care
- Always review the script before running
- Consider backing up important data before system maintenance
- The script is provided as-is with no warranties. Use at your own risk.
- Aggressive mode (-a) performs potentially destructive operations:
   - Forces complete database refresh (uses more bandwidth)
   - Completely clears package cache (requires redownloading all future packages)
   - Forcefully removes unused packages without confirmation
   - Removes entire cache directories rather than just contents


## Contribution

Contributions are welcome! Please:

- Open an issue to discuss proposed changes
- Submit pull requests with clear descriptions
- Maintain consistent coding style
- Update documentation (README.md) for new features

## License

MIT License - Free to use and modify

Created by Antonio Foti
