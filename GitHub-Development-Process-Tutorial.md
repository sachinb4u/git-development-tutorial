> Following steps give an overview of how GitHub development process will work.

1. Fork a repository
    * Go to https://github.wdf.sap.corp/OmniChannelBanking/git-demo
    * Click on Fork and select your account to fork the repository.
    * e.g. I fork repository to my account and URL would be `https://github.wdf.sap.corp/i313873/git-demo`

2. Clone forked repository locally
    * Go to local path where you want to clone repository e.g. C:\temp
    * Clone your forked repository
         * `C:\temp> git clone https://github.wdf.sap.corp/i313873/git-demo.git`
         * You will have repository cloned in `C:\temp\git-demo`

3. You must configure a remote that points to the upstream repository in Git to sync changes you make in a fork with the original repository. This also allows you to sync changes made in the original repository with the fork.
    * List the current configured remote repository for your fork 
      ```
        C:\temp\git-demo> git remote -v
        origin  git@github.wdf.sap.corp:i313873/git-demo.git (fetch)
        origin  git@github.wdf.sap.corp:i313873/git-demo.git (push)
      ```  
  
4. Specify a new remote upstream repository that will be synced with the fork.
      ```
        C:\temp\git-demo> git remote add upstream https://github.wdf.sap.corp/OmniChannelBanking/git-demo.git
      ```

5. Verify the new upstream repository you've specified for your fork.
      ```
        C:\temp\git-demo> git remote -v
        origin  git@github.wdf.sap.corp:i313873/git-demo.git (fetch)
        origin  git@github.wdf.sap.corp:i313873/git-demo.git (push)
        upstream        https://github.wdf.sap.corp/OmniChannelBanking/git-demo.git (fetch)
        upstream        https://github.wdf.sap.corp/OmniChannelBanking/git-demo.git (push)
      ```

6. Syncing a fork repository
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
    - Merge the changes from `upstream/master` into your local `master` branch. This brings your fork's `master` branch into sync with the upstream repository, without losing your local changes.
      ```
      C:\temp\git-demo> git merge upstream/master
      Updating 65aa625..9de8458
      Fast-forward
       README.md | 9 ++++++++-
       1 file changed, 8 insertions(+), 1 deletion(-)
      ```


	references:
		https://help.github.com/articles/configuring-a-remote-for-a-fork/

4. Synchronize the changes from upstream repository

5. Work on defect/feature

6. Create branch from master. e.g. 
	git checkout master
	git pull origin master
	git branch -b bcp-8732-account-details-issue

	# make some changes
	git add --all
	git commit -m "#BCP8732 - Fixed account details issue"
	
7. Push changes to your repository

	git push origin bcp-8732-account-details-issue

8. Go to https://github.wdf.sap.corp/ocb-labs/git-demo, create a new pull request for your changes

	- Select a reviewer or mention a developer who you think should be aware of changes you have done
	references:
		https://help.github.com/articles/creating-a-pull-request/
		https://help.github.com/articles/reviewing-proposed-changes-in-a-pull-request/
		
9. Reviwer reviews the code and adds comments

10. Reviwer proposes the changes in pull request

11. Developer makes changes in bcp-8732-account-details-issue branch and again the push the changes 
	# make changes for review comments
	git add --all
	git commit -m "#BCP8732 - addressed review comment to update documentation"
	git push origin bcp-8732-account-details-issue
	
12. Your changes will be see in the same pull request.

13. Reviewer approves the changes.

14. Developer deletes the branch from pull request UI.
