
Here's an updated Restore README that includes the additional files you've mentioned and offers guidance for restoring your Zsh and other related configurations.

Restore Terminal Configuration (Zsh and Other Dotfiles)
This guide walks you through restoring your terminal configuration, including Zsh, Powerlevel10k, and other settings from this repository after a system crash or when setting up a new machine.

Restore Instructions
Step 1: Clone the Repository
First, clone this backup repository onto your new system:

Open a terminal on the new system.
Run the following command to clone the repository:
bash
Copy code
git clone https://github.com/yourusername/terminal-backup.git
cd terminal-backup
Step 2: Restore Configuration Files
Once the repository is cloned, restore the following configuration files by copying them back to your home directory:

Zsh Configuration Files:

bash
Copy code
cp terminal-backup/.zshrc ~/
cp terminal-backup/.zprofile ~/
cp terminal-backup/.p10k.zsh ~/
cp terminal-backup/.zshrc.pre-oh-my-zsh ~/
.zshrc: The main Zsh configuration file.
.zprofile: Zsh login configuration, sourced at login.
.p10k.zsh: Powerlevel10k theme settings for Zsh.
.zshrc.pre-oh-my-zsh: Backup file created before installing Oh My Zsh (optional).
Optional Files:

If you have other saved files, such as .aliases, .gitconfig, or .vimrc, restore them using similar commands:
bash
Copy code
cp terminal-backup/.gitconfig ~/
cp terminal-backup/.vimrc ~/
cp -r terminal-backup/.ssh/ ~/
SSH Keys:

Ensure your SSH keys are copied correctly and permissions are set:
bash
Copy code
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
Step 3: Apply the Changes
After restoring the configuration files, you'll need to reload the terminal settings.

For Zsh users:

bash
Copy code
source ~/.zshrc
For Powerlevel10k users: If Powerlevel10k is not loading correctly, you may need to reinstall it. Follow the installation steps from the Powerlevel10k repository.

Verify SSH keys: Test if your SSH keys are working correctly by running:

bash
Copy code
ssh-add -l
Step 4: Verify the Restored Configurations
Zsh and Powerlevel10k: Open a new terminal session to ensure Zsh and Powerlevel10k load correctly with your previous configurations.

Git Configuration: Check your Git configuration with:

bash
Copy code
git config --list
Custom Aliases/Functions: Verify any custom aliases or functions in .zshrc by typing them in the terminal.

Troubleshooting
Permissions: If some configurations or SSH keys are not working, verify that file permissions are correct.

Example for SSH keys:

bash
Copy code
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub
Powerlevel10k: If Powerlevel10k isn't displaying correctly, ensure it's installed properly or re-run the configuration wizard:

bash
Copy code
p10k configure
Zsh as Default Shell: If Zsh is not set as your default shell, use:

bash
Copy code
chsh -s /bin/zsh
