## Macbook Development Environment Setup

### GitHub Setup
- Create SSH keys on macbook and add keys to GitHub profile. Just type `return` on prompts and keys get saved to `~/.ssh`.
    ```shell
    $ ssh-keygen
    ```
    `id_rsa` is private key and `id_rsa.pub` is public key

- Add SSH public key `~/.ssh/id_rsa.pub` to Github and verify that connection is working
    - Copy public key
     ```shell
     $ cat ~/.ssh/id_rsa.pub | pbcopy
    ```
    - Go to github.com settings and add a ssh key.

    - Test connection from your laptop to GitHub

    ```shell
    $ ssh -T git@github.wdf.sap.corp
    Hi i313873! You've successfully authenticated, but GitHub does not provide shell access.
    ```
- Installing Git
    - Open terminal on your MacBook
    - Just type `git` and enter, it will open window to ask you to install git. Follow the instructions and complete setup
    - Verify if git got installed
    ```shell
    $ git version
    git version 2.17.2 (Apple Git-113)
    ```