# Git-related issues and fixes

## Managing multiple Github accounts on a Single Computer

1. Ensure SSH keys are created for all Github accounts
```bash
# work in root .ssh folder
$ cd ~/.ssh

# create an ssh key specific to each Github account
# -f is for filename of the generated keys
# my suggestion is to use your Github username as the filename to prevent confusion
$ ssh-keygen -t rsa -C "your-email-address" -f "github-username"
# when prompted to add a passphrase, leave it empty
```

2. Add ssh keys to SSH agent
```bash
# do this for all Github accounts
# replace github-username with the filename used in the previous step
$ ssh-add -K ~/.ssh/github-username
```

3. Add public ssh keys to Github

    1. Copy public ssh keys to clipboard
    ```bash
    # do this for all Github accounts
    $ pbcopy < ~/.ssh/github-username.pub
    ```

    2. Open up Github on your browser
    3. Naviate to Settings > SSH and GPG keys > New SSH key
    4. Paste the public key from your clipboard to the key field and name the key

4. Create config file
```bash
# work in root .ssh folder (if not already in directory)
$ cd ~/.ssh

$ touch config
$ open config
```

5. Add accounts to the config file
```bash
# replace imran-school and imran personal with the filename as defined in Step 2

 #imran-school account
 Host github.com-imran-school
      HostName github.com
      User git
      IdentityFile ~/.ssh/imran-school

 #imran-personal account
 Host github.com-imran-personal
      HostName github.com
      User git
      IdentityFile ~/.ssh/imran-personal
```

6. Add git configs to each folder you will be working on
```bash
# in a school project folder
     git config user.email "school-email@email.com"
     git config user.name "Imran"

# in a personal project folder
     git config user.email "personal-email@email.com"
     git config user.name "Imran"
```