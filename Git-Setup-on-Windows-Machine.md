Follow below instructions to setup Git on your Windows machine.

## Git Installation on Windows

The most official build is available for download on the Git website. Just go to *__\\\uapune1.sybase.com\OCB_Softwares\Sachin\Git__* (intranet) or http://git-scm.com/download/win (internet) and the download will start automatically. 
Note that this is a project called Git for Windows, which is separate from Git itself; for more information on it, go to https://git-for-windows.github.io/.


## Git Configuration

Once you have installed Git, you will have to adapt the .gitconfig file to properly integrate with SAPs Git landscape:

1. Open a terminal
2. change into your user's directory e.g. C:\Users\i313873\
3. try to open `.gitconfig`
     * If the file does not exist, create a file '.gitconfig'
4. Paste the following into the .gitconfig file:
```
[user]
    name = <Your Real Name, e.g. Sachin Bhoslae>
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
[https]
    proxy = http://proxy.wdf.sap.corp:8080
[merge]
    renameLimit = 9000
    tool = /Applications/kdiff3.app
```
