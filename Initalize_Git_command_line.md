# Getting Started With Git

I recently set up a new computer and had to reinitialize my github locally. This is how I did it.

## In The Command Line

```
# Step 1: Install Xcode Command Line Tools
# Why: Git is included in the Xcode Command Line Tools, which are essential for software development on macOS.
xcode-select --install

# Step 2: Install Git
# Why: You need Git to manage and track your repositories.

# Check if Git is installed:
git --version
# Explanation: This command checks the current version of Git installed on your system. If it returns a version number, Git is already installed.

# If Git is not installed, you can install it using Homebrew:
# First, install Homebrew if you haven't already:
# Explanation: This command installs Homebrew, a package manager for macOS, which makes it easy to install software.
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then, install Git:
# Explanation: This command uses Homebrew to install Git.
brew install git

# Step 3: Set Up Git
# Why: Configuring Git with your user information is necessary for commit tracking.

# Set your username:
git config --global user.name "Your Name"
# Explanation: This command sets your Git username. The --global flag means this username will be used for all repositories on your computer.

# Set your email:
git config --global user.email "your-email@example.com"
# Explanation: This command sets your Git email address. The email address is used to associate your commits with your GitHub account.

# Step 4: Generate SSH Key
# Why: SSH keys allow you to securely connect to GitHub without needing to enter your username and password each time.

# Generate a new SSH key:
ssh-keygen -t ed25519 -C "your-email@example.com"
# Explanation: This command generates a new SSH key using the Ed25519 algorithm. The -C flag adds a label to the key with your email address.

# When prompted to "Enter a file in which to save the key," press Enter.
# Then, when prompted for a passphrase, you can enter one or leave it empty for no passphrase.
# Explanation: This saves the key to the default location (~/.ssh/id_ed25519) and optionally secures it with a passphrase.

# Add your SSH key to the ssh-agent:
eval "$(ssh-agent -s)"
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
# Explanation: The first command starts the ssh-agent in the background. The second command adds your SSH key to the ssh-agent and stores the passphrase in the macOS keychain.

# Copy the SSH key to your clipboard:
pbcopy < ~/.ssh/id_ed25519.pub
# Explanation: This command copies the public part of your SSH key to your clipboard, so you can easily paste it into GitHub.

# Step 5: Add SSH Key to GitHub
# Why: Adding your SSH key to GitHub allows you to authenticate without using a username and password.

# Go to GitHub (https://github.com) and log in.
# In the upper-right corner, click on your profile photo, then click Settings.
# In the user settings sidebar, click SSH and GPG keys.
# Click New SSH key.
# In the "Title" field, add a descriptive label for the new key.
# Paste your key into the "Key" field.
# Click Add SSH key.

# Step 6: Clone Your GitHub Repositories
# Why: Cloning your repositories allows you to have a local copy to work on.

# Go to the repository page on GitHub that you want to clone.
# Click the Code button and copy the SSH URL (e.g., git@github.com:username/repository.git).

# In Terminal, navigate to the directory where you want to clone the repository:
cd path/to/your/directory
# Explanation: This command changes the current working directory to the location where you want to clone your repository.

# Clone the repository:
git clone git@github.com:username/repository.git
# Explanation: This command clones the repository from GitHub to your local machine using the SSH URL.

# Step 7: Verify the Clone

# Navigate into the cloned repository:
cd repository
# Explanation: This command changes the current working directory to the newly cloned repository.

# Verify the remote URL:
git remote -v
# Explanation: This command lists the remote repositories configured for the current repository. You should see the URL of your repository listed.

# Additional Step: Verifying the SSH Key

# View the Public SSH Key:
cat ~/.ssh/id_ed25519.pub
# Explanation: This command displays the contents of the id_ed25519.pub file, which is your public SSH key.

# Copy the Public SSH Key to Clipboard:
pbcopy < ~/.ssh/id_ed25519.pub
# Explanation: This command copies the contents of the id_ed25519.pub file to your clipboard, making it easy to paste into GitHub or any other service that requires your public key.

# View the Private SSH Key (not usually necessary):
cat ~/.ssh/id_ed25519
# Explanation: This command displays the contents of the id_ed25519 file, which is your private SSH key. Be very careful with this key; it should not be shared with anyone.
```

