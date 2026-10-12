# ⚡ Modular Zsh & Starship Configuration

A clean, blazing-fast, and modular Zsh configuration with custom **Starship** prompt styling, automatic plugin management, and modern CLI tooling replacements.

Tested and optimized for **CachyOS / Arch Linux**, **Ubuntu**, and **WSL**.

---

## 📁 Architecture & File Layout

This setup follows the **XDG Base Directory specification** and keeps all Zsh configurations cleanly organized inside `~/.config/zsh/` rather than cluttering `$HOME`:

| File | Purpose |
|---|---|
| **`.zshenv`** | Sets XDG base directories, default editor (`nano`/`nvim`), pagers, and `$PATH`. |
| **`.zshrc`** | Core shell behaviors, history deduplication (`100k` lines), and WSL path filtering. |
| **`prompt.zsh`** | Starship prompt initialization and environment settings. |
| **`starship.toml`** | Custom Starship theme with username highlight and OS distribution glyphs (CachyOS, Arch, Ubuntu, macOS). |
| **`aliases.zsh`** | Modern CLI tool aliases (`eza`, `bat`, `ripgrep`, `nvim`, `lf`, `git`). |
| **`bindings.zsh`** | Keybindings for command-line navigation and editing. |
| **`fzf.zsh`** | Fuzzy search bindings and interactive completion hooks. |
| **`plugins.zsh`** | Zero-dependency, auto-cloning plugin manager for fast shell startups. |

---

## 📦 Bundled Plugins (Auto-Installed)

When Zsh starts for the first time, `plugins.zsh` automatically clones and sources these 4 essential plugins:

1. **`zsh-autosuggestions`**: Fish-like fast command suggestions.
2. **`fast-syntax-highlighting`**: Real-time command syntax coloring.
3. **`zsh-history-substring-search`**: Up/Down arrow search matching typed prefixes.
4. **`zsh-vi-mode`**: Better Vi keybindings for command-line editing.

To update all plugins at any time, run:
```bash
zplugin-update
```

---

## 🛠️ Recommended CLI Utilities

For the full experience with all aliases enabled, install:

```bash
# Arch / CachyOS
sudo pacman -S --needed zsh starship eza bat ripgrep fzf zoxide neovim

# Ubuntu / Debian
sudo apt install zsh fzf ripgrep neovim
# (Install starship, eza, bat, and zoxide via their official package managers or cargo)
```

---

## 🚀 Installation & Setup

### 1. Clone into `~/.config/zsh`
```bash
git clone https://github.com/Mhdomer/zsh-dotfiles.git ~/.config/zsh
```

### 2. Point Zsh to `~/.config/zsh`
Add this single line to your `~/.zshenv` (or `~/.zshrc`):
```bash
export ZDOTDIR="$HOME/.config/zsh"
```

Or symlink `.zshrc` directly:
```bash
ln -s ~/.config/zsh/.zshrc ~/.zshrc
ln -s ~/.config/zsh/.zshenv ~/.zshenv
```

### 3. Launch Zsh
```bash
zsh
```
All plugins will automatically clone on first run, Starship will load your custom prompt, and you're ready to go!
