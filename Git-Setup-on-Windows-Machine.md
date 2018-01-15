Follow below instructions to setup Git on your Windows machine.

## Git Installation on Windows

- The most official build is available for download on the Git website. Just go to *__\\\uapune1.sybase.com\OCB_Softwares\Sachin\Git__* (intranet) or http://git-scm.com/download/win (internet) and the download will start automatically. 

- Install WinMerge for merging changes in case of mergconflict. **_\\\uapune1.sybase.com\OCB_Softwares\Sachin\Git_** or http://winmerge.org/


## Git Configuration

Once you have installed Git, you will have to adapt the .gitconfig file to properly integrate with SAPs Git landscape:

1. Open a terminal
2. change into your user's directory e.g. C:\Users\i313873\
3. try to open `.gitconfig`
     * If the file does not exist, create a file '.gitconfig'
4. Paste the following into the .gitconfig file:
```
[user]
    name = <Your Real Name, e.g. Sachin Bhosale>
    email = <your sap email address, e.g. s.bhosale@sap.com>

[color]
    ui = true
    status = auto
    branch = auto
 
[core]
    autocrlf = true
    filemode = false

[http]
    proxy = http://proxy.wdf.sap.corp:8080
    sslVerify = false

[https]
    proxy = http://proxy.wdf.sap.corp:8080

[mergetool]
    prompt = false
    keepBackup = false
    keepTemporaries = false
	
[merge]
    tool = winmerge

[mergetool "winmerge"]
    name = WinMerge
    trustExitCode = true
    cmd = "/c/Program\\ Files\\ \\(x86\\)/WinMerge/WinMergeU.exe" -u -e -dl \"Local\" -dr \"Remote\" $LOCAL $REMOTE $MERGED

[diff]
    tool = winmerge

[difftool "winmerge"]
    name = WinMerge
    trustExitCode = true
    cmd = "/c/Program\\ Files\\ \\(x86\\)/WinMerge/WinMergeU.exe" -u -e $LOCAL $REMOTE
```
5. Save and close the file.


That's it. What this does is the following:

* `user.name`
Needs to be your full name. For example, John Smith. Git stores your full name in every commit that you create. Therefore, it is important to set this property before you start committing your changes. In case this property is not set, Git will take some incorrect default value, such as your user.name; most likely it will be your dXXXXXX or iXXXXXX username.
* `user.email`
Your SAP e-mail address. Git stores your e-mail address in every commit that you create. Unfortunately, the default e-mail that Git gets from the operating system is iXXXXXX@your-machine-name, which is not your SAP e-mail address. Therefore, it is important to set this property before you start committing your changes. In case this property is not set Git will take some default as your `user.email`. 

* `core.autocrlf`
Defines CRLF <-> LF conversion rules for checkout and commit of text files. This property tends to be ignored by developers, until they run into line-ending issues. On Windows machines, when you hit 'return' at the end of a line, Windows adds two invisible characters a CR (carriage return) and an LF (line feed) - hence CRLF - on Linux and Mac only an LF (line feed) char is added. Thus if you are developing an a team mixed with Windows / Mac users, the line endings - if not properly converted - will show up as differences and cause merge conflicts.
A common symptom for that problem is that a developer clones a Git repository. Immediately after that the git status command reports a lot of changes done locally. The developer is sure that there were no changes done locally and executes git diff to find out what the changes are. Git reports differences in line endings. 
This issue is often caused by usage of different settings for the core.autocrlf property within one and the same development team.
You can find a good explanation of this property in the book Pro Git. See the Git Configuration chapter and search for core.autocrlf.

* `core.filemode`
This property defines whether to ignore the executable bit difference. It can also cause mysterious differences, immediately after cloning a repository. The reason behind is that unlike OSX/Linux, Windows does not support the executable bit on files.
All Windows users should set this property to false to avoid running into this issue.


### Generate SSH key

- Search git bash in start and open it

- Run the command `ssh-keygen -t rsa -C "your_email@example.com"`. Press enter on prompt. It will save below 2 files in /c/users/i313873/.ssh folder
    * id_rsa - private key
    * id_rsa.pub - public key

- Go to https://github.wdf.sap.corp and follow https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/ to add your SSH key to your GitHub account.

- After adding SSH key, open Git Bash and run below command to see if authentication is successful
```
    I313873@PNQN50910881A MINGW64 ~
    $ ssh -T git@github.wdf.sap.corp
    Hi i313873! You've successfully authenticated, but GitHub does not provide shell access.
```