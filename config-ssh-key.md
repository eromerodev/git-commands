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
ssh-add -K ~/.ssh/id_ed25519_github
```

Note: replace `id_ed25519_github` with the name of your own SSH key.

#### Set up the config file

If you dont already have the `config` file inside your `/.ssh` folder, create one:

```bash
# Create
touch ~/.ssh/config

# Paste the followint
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

### 3. Add the SSH key to Github

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

More info: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh
