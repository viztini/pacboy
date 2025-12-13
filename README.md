# pacboy, the cutest arch linux package manager 🎀

pacboy is a cute and interactive command-line package manager for Arch Linux, designed to simplify `pacman` and AUR operations with a friendly (but powerful) interface.

It aims to feel playful on the surface while still exposing the full sharp edges of Arch underneath.

## Features

* **Interactive Search:** Search official repositories and the AUR using a `curses`-based interactive selector.
* **Install:** Install official and AUR packages.
* **Remove:** Remove installed packages.
* **Force Remove:** Remove packages while ignoring dependencies (dangerous).
* **Update:** Fully update your system.
* **Clean Cache:** Clean pacman’s package cache.
* **Clean Orphans:** Detect and remove orphaned packages.
* **Global Force Mode:** One flag to force *any* command to run without confirmations.
* **Themed Output:** Colorful, cute, and readable terminal output.

## Installation

To install `pacboy`:

1. Clone the repository:
   ```bash
   git clone https://github.com/viztini/pacboy.git

2. Change into the project directory:

   ```bash
   cd pacboy
   ```

3. Make the installer executable:

   ```bash
   chmod +x install.sh
   ```

4. Run the installation script:

   ```bash
   ./install.sh
   ```

The installer will:

* Copy the `pacboy` script to `~/.local/bin/`
* Mark it as executable

## Usage

After installation, run `pacboy` from anywhere:

```bash
pacboy <command> [arguments] [--force]
```

### Global Flags

* `--force`
  Forces **any command** to execute immediately:

  * Skips confirmation prompts
  * Bypasses safety pauses
  * Enables destructive operations without asking

**Use with caution. This flag exists to give you full control, not to protect you.**

### Available Commands

* `pacboy install <package(s)>`
  Install one or more packages (official or AUR).

* `pacboy remove <package(s)>`
  Remove one or more installed packages.

* `pacboy fremove <package(s)>`
  Force-remove packages using `pacman -Rdd` (may break your system).

* `pacboy search <query>`
  Search packages interactively from repos and the AUR.

* `pacboy update`
  Update the entire system (`pacman -Syu`).

* `pacboy clean`
  Clean the pacman package cache.

* `pacboy clean-orphan`
  Find and remove orphaned packages.

### Examples

Safe, interactive orphan cleanup:

```bash
pacboy clean-orphan
```

Force orphan removal without confirmation:

```bash
pacboy clean-orphan --force
```

Force a system update without prompts:

```bash
pacboy update --force
```

Force-remove a broken package:

```bash
pacboy fremove linux-firmware --force
```

## Zsh Compatibility

`pacboy` works seamlessly with Zsh.
Make sure `~/.local/bin` is in your `PATH`. If not, add this to your `.zshrc`:

```zsh
export PATH="$HOME/.local/bin:$PATH"
```

## Contributing

Pull requests, issues, and experiments are welcome.
This project embraces personality, but correctness always wins.

Arch is sharp.
pacboy just gives it a cute handle.

