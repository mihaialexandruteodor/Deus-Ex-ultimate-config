from [this steam tutorial](https://steamcommunity.com/sharedfiles/filedetails/?id=2967089130)

# Deus Ex: Game of the Year Edition Linux Guide

## Preliminary Notes

### Introduction
This guide will take you through the steps needed to get the game playing near-flawlessly on modern systems running Linux. The focus is to make it as easy and digestible so that any Linux user can follow each step!

> This guide will **NOT** show how to install complete overhauls or mods that alter the gameplay.

Below you'll see my distro and machine specifications. The guide is based on this setup. If your system is drastically different, some additional research may be required.

### My System & Machine Specifications
- **OS:** Arch Linux  
- **Kernel:** 6.2.11-arch1-1  
- **CPU:** Intel Core i5-4690K @ 3.50GHz  
- **GPU:** NVIDIA GeForce GTX 970  
- **GPU Driver:** NVIDIA 530.41.03  
- **RAM:** 16GB @ 2400MHz  

## Prerequisites

### Basic Requirements
- Up-to-date Steam copy of Deus Ex  
- Latest drivers for your Linux distro and GPU  
- Steam's Proton function enabled  
- Protontricks  
- Any terminal emulator  

> Check all requirements above before reporting issues.

### Enabling Steam's Proton
1. Open Steam and click **Steam > Settings > Steam Play**  
2. Tick both boxes  
3. Select **Proton Experimental** in the drop-down menu  
4. Click **OK**  

### Installing Protontricks

**Arch-based distros:**
```bash
paru -S protontricks
# OR
yay -S protontricks
