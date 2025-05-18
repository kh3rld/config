# Config

This repository contains my personal system configurations for various tools and applications. It's designed to make setting up a new system or maintaining existing configurations easier.

## Repository Structure

- `nvim/` - Neovim configuration files
  - `lua/` - Lua-based Neovim configuration
  - `init.lua` - Main Neovim initialization file
  - `lazyvim.json` - LazyVim plugin manager configuration
  - `lazy-lock.json` - Plugin lock file

- `kitty/` - Kitty terminal emulator configuration
  - `kitty.conf` - Main configuration file
  - `current-theme.conf` - Current theme settings
  - `kitty.conf.bak` - Backup configuration

- `NetworkManager/` - NetworkManager configuration
  - `conf.d/` - NetworkManager configuration directory

- `changemac@.service` - Systemd service for MAC address management

## Setup Instructions

### Prerequisites

- Linux-based operating system
- Git
- Neovim (for nvim configuration)
- Kitty terminal emulator (for kitty configuration)
- NetworkManager (for network configuration)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/kh3rld/config.git ~/.config
   ```

2. Create necessary symlinks:
   ```bash
   # Neovim
   ln -s ~/.config/nvim ~/.config/nvim

   # Kitty
   ln -s ~/.config/kitty/kitty.conf ~/.config/kitty/kitty.conf

   # NetworkManager
   sudo ln -s ~/.config/NetworkManager/conf.d/* /etc/NetworkManager/conf.d/
   ```

3. Install required dependencies:
   ```bash
   # For Neovim
   nvim --headless -c 'Lazy sync' -c 'qa'

   # For Kitty
   kitty +kitten themes --reload-in=all
   ```

## Configuration Details

### Neovim Configuration
The Neovim configuration uses LazyVim as the plugin manager. Key features:
- Lua-based configuration
- Lazy plugin management
- Custom keybindings and settings

### Kitty Configuration
Kitty terminal configuration includes:
- Custom theme settings
- Font configuration
- Window management settings
- Keyboard shortcuts

### NetworkManager Configuration
NetworkManager settings for:
- Network interface management
- Connection profiles
- DNS settings

### MAC Address Management
The `changemac@.service` file provides a systemd service for managing MAC addresses.

## Maintenance

### Updating Configurations
1. Pull the latest changes:
   ```bash
   git pull origin main
   ```

2. Reload configurations:
   ```bash
   # Reload Neovim plugins
   nvim --headless -c 'Lazy sync' -c 'qa'

   # Reload Kitty
   kitty +kitten themes --reload-in=all

   # Reload NetworkManager
   sudo systemctl restart NetworkManager
   ```

### Adding New Configurations
1. Create new configuration files in the appropriate directory
2. Update this README with new configuration details
3. Commit and push changes:
   ```bash
   git add .
   git commit -m "Add new configuration: [description]"
   git push origin main
   ```

