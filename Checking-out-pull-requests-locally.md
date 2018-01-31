>How to get Pull Request locally for review or to work on someone else's work.

1. Fetch the reference to the pull request based on its ID number, creating a new branch in the process. e.g. we get the pull request `3` from `git-demo`[repository pull requests](https://github.wdf.sap.corp/OmniChannelBanking/git-demo/pulls?q=is%3Apr+is%3Aclosed).
    ```
    git fetch upstream pull/ID/head:BRANCHNAME
    git fetch upstream pull/3/head:pr/3
    ```

2. Switch to the new branch that's based on this pull request:
    ```
    [master] $ git checkout pr/3
    Switched to a new branch 'pr/3'
    ```

3. At this point, you can do anything you want with this branch. You can run some local tests, or merge other branches into it, including master. Make modifications as you see fit!

4. When you're ready, you can push the new branch up:
    ```
    [pull-inactive-pull-request] $ git push origin BRANCHNAME
    Counting objects: 32, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (26/26), done.
    Writing objects: 100% (29/29), 74.94 KiB | 0 bytes/s, done.
    Total 29 (delta 8), reused 0 (delta 0)
    To https://github.com/username/repository.git
     * [new branch]      BRANCHNAME -> BRANCHNAME
    ```

5. Create a new pull request with your new branch.