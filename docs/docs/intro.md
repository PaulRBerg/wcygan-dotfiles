---
sidebar_position: 1
slug: /
---

# Introduction

Welcome to my dotfiles repository! This collection provides modern developer configuration files with safe installation and easy management.

## Features

- **🚀 Modern CLI Tools**: Configurations for ripgrep, fd, bat, eza, fzf, and more
- **🐟 Fish Shell**: Full fish configuration with functions, abbreviations, and aliases  
- **📦 Nix Package Management**: Reproducible tool installation via flake.nix
- **🔗 Safe Symlink Management**: Automated config linking with backup/restore
- **🎯 Per-Project Environments**: nix-direnv pattern for isolated development
- **✅ CI/CD Ready**: GitHub Actions with matrix testing across macOS, Ubuntu, Fedora
- **🛡️ Idempotent Scripts**: All operations safe to run multiple times

## Quick Start

```bash
# Clone the repository
git clone https://github.com/wcygan/dotfiles.git
cd dotfiles

# Install Nix package manager (if not already installed)
curl -L https://nixos.org/nix/install | sh

# Run tests
make test-pre

# Link configurations
make link-config
```

## Repository Structure

```
dotfiles/
├── config/           # Configuration files (fish, starship, etc.)
├── scripts/          # Installation and utility scripts
├── flake.nix         # Nix package definitions
├── tests/            # Test suites
└── docs/             # This documentation site
```

## Principles

- **Idempotent**: Every script is safe to run twice
- **Cross-platform**: Works on macOS, Ubuntu, and Fedora
- **Minimal surface area**: Simple configs under `config/`, packages in `flake.nix`
- **Test-first operations**: Pre-flight checks before any changes
- **Rollbackable**: All changes can be reverted

## Getting Help

- Check the [README](https://github.com/wcygan/dotfiles) for detailed setup instructions
- Open an [issue](https://github.com/wcygan/dotfiles/issues) for bugs or questions
- Submit a [pull request](https://github.com/wcygan/dotfiles/pulls) for improvements