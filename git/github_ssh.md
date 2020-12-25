# GitHub SSH

## Linux

```bash
# list existing SSH keys
$ ls -al ~/.ssh

# Generating new SSH key
$ $ ssh-keygen -t ed25519 -C your_email@example.com

# This will ask for a secure passphrase when generating key
# remember this passphrase as it will be needed in the future

# This will ask for a file name to save the key
# assume the file is saved as "id_ed25519_examplefile"

# add this ssh key to the SSH agent
$ ssh-agent ~/.ssh/id_ed25519_examplefile
```

Add this SSH key (from ``~/.ssh/id_ed25519_examplefile.pub`` file) to GitHub account.

**To use multiple SSH keys for different accounts, we have to use ``~/.ssh/config`` file**

assuming we have 2 github accounts: **hello** and **world**, the ``config`` file will be like:

```bash
# ~/.ssh/config

# hello account
Host gh-hello
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_hello

# world account
Host gh-world
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_world
```

``gh-hello`` and ``gh-world`` are user defined terms. Use this while setting the **remote** location of a github repository.

```bash
# creating repository
$ git init
$ git remote add origin git@gh-hello:hello/repo_name.git

# gh-hello : same as 'Host' in config file
# hello : github username
# repo_name : repository name

# check current remote url
$ git remote -v

# change remote url
$ git remote set-url origin git@gh-hello:hello/repo_name.git
```

----
### Links
1. [Connecting to GitHub with SSH - docs.github.com](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/connecting-to-github-with-ssh)
2. [Git Push & Pull from multiple accounts - medium.com](https://therajanmaurya.medium.com/git-push-pull-with-two-different-account-and-two-different-user-on-same-machine-a85f9ee7ec61)
