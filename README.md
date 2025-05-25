# Will's Dotfiles

A comprehensive shell configuration setup with modular organization, supporting both bash and zsh across macOS, Linux, and Windows. Built with modern Deno TypeScript for type safety and cross-platform reliability.

## 🚀 Quick Installation

### Prerequisites

First, install Deno if you haven't already:

**macOS/Linux:**
```bash
curl -fsSL https://deno.land/install.sh | sh
```

**Windows (PowerShell):**
```powershell
irm https://deno.land/install.ps1 | iex
```

**Alternative methods:**
- **Homebrew**: `brew install deno`
- **Cargo**: `cargo install deno --locked`
- **npm**: `npm install -g @deno/cli`

### Installation

The safest and most modern way to install these dotfiles using type-safe Deno scripts:

```bash
git clone https://github.com/wcygan/dotfiles.git && cd dotfiles
deno run --allow-all install-safely.ts
```

**Or use the convenient Deno task:**
```bash
git clone https://github.com/wcygan/dotfiles.git && cd dotfiles
deno task install
```

**What this does:**
- ✅ Auto-detects your shell (zsh/bash)
- ✅ Backs up existing dotfiles with timestamp
- ✅ Installs new dotfiles from repository
- ✅ Reloads shell configuration
- ✅ Provides rollback instructions

**Benefits of Deno approach:**
- ✅ Type-safe with comprehensive error handling
- ✅ Cross-platform compatibility (macOS, Linux, Windows)
- ✅ Modern async/await patterns
- ✅ Better user feedback and validation
- ✅ No shell script dependencies
- ✅ Consistent behavior across all platforms

## 🔄 Rollback Support

If you need to restore your original configuration:

```bash
deno run --allow-all rollback.ts ~/.dotfiles-backup-20240525-102500
# Or use the task:
deno task rollback ~/.dotfiles-backup-20240525-102500
```

The installation script will tell you the exact backup directory path.

## 📋 What Gets Installed

### Core Shell Files
- `.zshrc` / `.bashrc` - Main shell configuration
- `.bash_profile` - Bash login shell settings
- `.aliases` - Command shortcuts and modern CLI tool replacements
- `.functions` - Useful shell functions
- `.exports` - Environment variables
- `.path` - PATH modifications
- `.extra` - Tool integrations (git, fzf, mise, etc.)

### Editor Configurations
- `.vimrc` - Vim editor configuration
- `cursor/` - Cursor IDE settings
- `zed/` - Zed editor settings  
- `vscode/` - VS Code settings

### Cross-Platform Support
- `profile.ps1` - PowerShell configuration for Windows
- Platform-specific adaptations in `.platform`

## 🔧 Customization

### Adding Personal Configurations

Create a `.extra` file in your home directory for personal customizations:

```bash
# Git credentials
GIT_AUTHOR_NAME="Your Name"
GIT_AUTHOR_EMAIL="your.email@example.com"

# Custom aliases  
alias myproject="cd ~/path/to/project"

# API keys and secrets
export API_KEY="your-secret-key"
```

### Shell-Specific Additions

- **Zsh**: Add to `~/.zshrc.local`
- **Bash**: Add to `~/.bashrc.local`  
- **PowerShell**: Add to `$PROFILE.CurrentUserCurrentHost`

## 📦 Included Tools & Integrations

### Modern CLI Replacements
- `bat` instead of `cat` (syntax highlighting)
- `exa`/`eza` instead of `ls` (modern file listing)
- `fd` instead of `find` (faster file search)
- `rg` (ripgrep) for text search
- `fzf` for fuzzy finding

### Development Tools
- **Git**: Enhanced aliases and configuration
- **Docker**: Container management shortcuts
- **Kubernetes**: kubectl aliases and functions  
- **Language Tools**: Go, Rust, Java, Node.js, Python
- **Editors**: Cursor, Zed, VS Code, Vim

### System Integrations
- **mise**: Development environment manager
- **Homebrew**: Package management (macOS/Linux)
- **zsh-syntax-highlighting**: Command syntax highlighting
- **fzf**: Fuzzy file/command search

## 🧪 Testing Your Installation

After installation, test these common shortcuts:

```bash
# Modern CLI tools
ll          # Better ls with exa
cat file    # Syntax highlighted with bat  
find .      # Faster search with fd

# Development shortcuts
d           # Open development workspace in Cursor
k get nodes # kubectl shortcut
cgr         # cargo run
mm          # git main branch helper
dcr web     # docker-compose restart web

# SSH shortcuts (customize in .aliases)
m0          # SSH to main-0 host
k1          # SSH to k8s-1 host
```

## 🔄 Staying Updated

### Automatic Updates
The installation script automatically updates the repository during installation.

### Manual Updates
```bash
cd ~/dotfiles  # or wherever you cloned
git pull origin main
deno task install:force
```

## 🛠️ Prerequisites

### Required
- [Deno](https://deno.land) runtime
- Git
- Compatible with any shell (zsh, bash, fish, etc.)

### Optional Enhancements
- [Homebrew](https://brew.sh) (macOS/Linux)
- [bat](https://github.com/sharkdp/bat): `brew install bat`
- [exa](https://github.com/ogham/exa): `brew install exa`  
- [fd](https://github.com/sharkdp/fd): `brew install fd`
- [fzf](https://github.com/junegunn/fzf): `brew install fzf`
- [mise](https://github.com/jdx/mise): Development environment manager

## 🚨 Emergency Restore

If something goes wrong:

1. **Find your backup**: `ls ~/.dotfiles-backup-*`
2. **Restore**: `deno task rollback <backup-dir>`
3. **Manual restore**: `cp ~/.dotfiles-backup-*/.[a-z]* ~/`

## ⚙️ Advanced Usage

### Available Deno Tasks
```bash
deno task install        # Install dotfiles (with prompts)
deno task install:force  # Install dotfiles (skip prompts)
deno task rollback       # Rollback to backup
deno task check          # Type check scripts
deno task help           # Show help
```

### Direct Script Usage
```bash
# Force Installation (Skip Prompts)
deno run --allow-all install-safely.ts --force

# Help and Options
deno run --allow-all install-safely.ts --help
deno run --allow-all rollback.ts --help
```

### Development and Testing
```bash
# Check TypeScript types
deno task check

# Run with specific permissions
deno run --allow-read --allow-write --allow-run install-safely.ts
```

## 🎯 Project Goals

- **Type-Safe**: Deno TypeScript scripts for reliability and maintainability
- **Cross-Platform**: Works identically on macOS, Linux, and Windows
- **Modern**: Embraces new tools while maintaining compatibility
- **Safe**: Always backup before changes with rollback support
- **Modular**: Each configuration aspect in separate files
- **Zero Dependencies**: No shell script dependencies or external tools required

## 🔍 File Structure

```
dotfiles/
├── install-safely.ts    # Main installation script
├── rollback.ts          # Rollback script
├── deno.json           # Deno configuration and tasks
├── .zshrc              # Zsh configuration
├── .bash_profile       # Bash configuration
├── .aliases            # Command shortcuts
├── .functions          # Shell functions
├── .exports            # Environment variables
├── .path               # PATH modifications
├── .extra              # Tool integrations
├── .vimrc              # Vim configuration
├── cursor/             # Cursor IDE settings
├── zed/                # Zed editor settings
├── vscode/             # VS Code settings
└── profile.ps1         # PowerShell configuration
```

## 📄 License

MIT License - feel free to fork and customize for your own use!

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test on multiple platforms with `deno task check`
5. Submit a pull request

---

*These dotfiles represent years of shell customization and modern development tool integration. Built with Deno TypeScript for type safety, cross-platform compatibility, and modern development practices.*