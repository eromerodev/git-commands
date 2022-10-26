# Setting SSH (macOS)

Set up SSH on your mac to connect to your Github account.

### 1. Generate SSH key on your computer

```bash
# Run the following command:

ssh-keygen -t ed25519 -C "<email>"

# -C flag set a comment or label for indentifying your SSH key
# -t ed25519 sets the encryption algorithm
```

### 2. Add the SSH key to the ssh-agent

```bash
# Start the ssh-agent in the background:
eval "$(ssh-agent -s)"

# (or)
exec ssh-agent zsh

# Add th SSH key
ssh-add --apple-use-keychain ~/.ssh/id_ed25519_github
```

Note: replace `id_ed25519_github` with the name of your own SSH key.

#### Set up the config file

If you dont already have the `config` file inside your `/.ssh` folder, create one:

```bash

# Modify your ~/.ssh/config 
open ~/.ssh/config

# If the file doesn't exist, create the file 
touch ~/.ssh/config

# Paste the following content
Host *.github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519_github
```

### 3. Add the SSH key to Github

```bash
pbcopy < ~/.ssh/id_ed25519_github.pub
```

More info: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh
