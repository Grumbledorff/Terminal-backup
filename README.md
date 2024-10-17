
# Terminal Configuration Backup and Restore

This repository provides a method for backing up and restoring your terminal configuration files on macOS. If your system crashes or you're migrating to a new machine, this guide will help you restore your terminal settings, including Zsh configurations, Powerlevel10k themes, Git settings, and SSH keys.

## Features

- Backup critical terminal configuration files like `.zshrc`, `.bash_profile`, `.gitconfig`, `.vimrc`, and SSH keys.
- Restore all settings on any machine easily.
- Simple Git-based version control for tracking configuration changes.
- Flexible file inclusion—add or remove files as needed.

---

## Table of Contents

1. [Backup Instructions](#backup-instructions)
2. [Restore Instructions](#restore-instructions)
3. [Files to Backup](#files-to-backup)
4. [Troubleshooting](#troubleshooting)

---

## Backup Instructions

### Step 1: Clone the Repository

To start, clone this repository to the location where you'd like to store your configuration backups:

```bash
git clone https://github.com/yourusername/terminal-backup.git
cd terminal-backup
```

### Step 2: Add Configuration Files

Edit the `.gitignore` file if needed and include any important configuration files. Some common files include:

- `.zshrc` (Zsh configuration)
- `.bash_profile` (Bash configuration)
- `.p10k.zsh` (Powerlevel10k theme configuration)
- `.gitconfig` (Git configuration)
- `.vimrc` (Vim editor configuration)
- `.ssh/` directory (SSH keys and configuration)

Add the files to the repository:

```bash
git add ~/.zshrc ~/.bash_profile ~/.p10k.zsh ~/.gitconfig ~/.vimrc ~/.ssh/
```

### Step 3: Commit and Push Changes

Commit the added files and push them to the repository:

```bash
git commit -m "Backup terminal configuration files"
git push origin main
```

---

## Restore Instructions

### Step 1: Clone the Repository

On a new system or after a system crash, clone the repository:

```bash
git clone https://github.com/yourusername/terminal-backup.git
cd terminal-backup
```

### Step 2: Restore Configuration Files

Copy the backed-up configuration files to your home directory:

```bash
cp terminal-backup/.zshrc ~/
cp terminal-backup/.bash_profile ~/
cp terminal-backup/.p10k.zsh ~/
cp terminal-backup/.gitconfig ~/
cp terminal-backup/.vimrc ~/
cp -r terminal-backup/.ssh/ ~/
```

### Step 3: Apply Changes

For Zsh users:
```bash
source ~/.zshrc
```

For Bash users:
```bash
source ~/.bash_profile
```

### Step 4: Verify the Restored Configurations

Open a new terminal session and check that everything is working as expected.

---

## Files to Backup

The following are common configuration files to back up:

- `.zshrc` – Zsh configuration file.
- `.bash_profile` – Bash configuration file.
- `.p10k.zsh` – Powerlevel10k theme configuration.
- `.gitconfig` – Git settings.
- `.vimrc` – Vim editor configuration.
- `.ssh/` – SSH keys and configuration.

---

## Troubleshooting

- **Permissions**: Ensure file permissions are correct for SSH keys:
```bash
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
```

- **Zsh as Default Shell**: Set Zsh as the default shell if needed:
```bash
chsh -s /bin/zsh
```

- **Powerlevel10k**: If Powerlevel10k doesn't work correctly, reinstall it:
```bash
p10k configure
```

By following this guide, you will be able to restore all your terminal configurations easily.
