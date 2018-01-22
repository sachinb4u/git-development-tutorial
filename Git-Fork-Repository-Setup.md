> Following steps explain how to setup forked repository for the development

### Fork a repository
* Go to https://github.wdf.sap.corp/OmniChannelBanking/git-demo
* Click on Fork and select your account to fork the repository.
* e.g. I fork repository to my account and URL would be `https://github.wdf.sap.corp/i313873/git-demo`

### Clone forked repository locally
* Go to local path where you want to clone repository e.g. C:\temp
* Clone your forked repository
    * `C:\temp> git clone https://github.wdf.sap.corp/i313873/git-demo.git`
    * You will have repository cloned in `C:\temp\git-demo`

### Configure Upstream repository
* You must configure a remote that points to the upstream repository in Git to sync changes you make in a fork with the original repository. This also allows you to sync changes made in the original repository with the fork.
    * List the current configured remote repository for your fork 
      ```
        C:\temp\git-demo> git remote -v
        origin  git@github.wdf.sap.corp:i313873/git-demo.git (fetch)
        origin  git@github.wdf.sap.corp:i313873/git-demo.git (push)
      ```
* Specify a new remote upstream repository that will be synced with the fork.
```
    C:\temp\git-demo> git remote add upstream https://github.wdf.sap.corp/OmniChannelBanking/git-demo.git
```
* Verify the new upstream repository you've specified for your fork.
```
    C:\temp\git-demo> git remote -v
    origin  git@github.wdf.sap.corp:i313873/git-demo.git (fetch)
    origin  git@github.wdf.sap.corp:i313873/git-demo.git (push)
    upstream        https://github.wdf.sap.corp/OmniChannelBanking/git-demo.git (fetch)
    upstream        https://github.wdf.sap.corp/OmniChannelBanking/git-demo.git (push)
```

### Syncing repository with Upstream changes

- Fetch the branches and their respective commits from the upstream repository.
```
    C:\temp\git-demo> git fetch upstream
    remote: Counting objects: 1, done.
    remote: Total 1 (delta 0), reused 1 (delta 0), pack-reused 0
    Unpacking objects: 100% (1/1), done.
    From github.wdf.sap.corp:OmniChannelBanking/git-demo
     * [new branch]      master     -> upstream/master
```	
- Check out your fork's local `master` branch.
```
    C:\temp\git-demo> git checkout master
    Switched to branch 'master'
```
- Merge the changes from `upstream/master` into your local `master` branch. This brings your fork's `master` branch in sync with the upstream repository, without losing your local changes.
```
      C:\temp\git-demo> git merge upstream/master
      Updating 65aa625..9de8458
      Fast-forward
       README.md | 9 ++++++++-
       1 file changed, 8 insertions(+), 1 deletion(-)
```
- Push your changes to forked repository to keep it sync with upstream repository
```
      C:\temp\git-demo> git push origin master
      Counting objects: 10, done.
      Delta compression using up to 4 threads.
      Compressing objects: 100% (7/7), done.
      Writing objects: 100% (10/10), 1.22 KiB | 0 bytes/s, done.
      Total 10 (delta 2), reused 0 (delta 0)
      remote: Resolving deltas: 100% (2/2), done.
      To github.wdf.sap.corp:i313873/git-demo.git
         65aa625..9de8458  master -> master
```

# 💡 Important Note
> You need to synchronize your forked local repository regularly like you take latest changes from P4 repository and working on latest code.
>   * Before working on new defect or feature sync the repository with upstream repository.