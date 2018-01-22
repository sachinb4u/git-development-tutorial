> Following sections gives idea about frequently used actions on Git

### Saving  changes
1. Add files to staging
```
git add .           # adds all modified files in current directory and sub-directory
git add <file-name> # adds file
git add <folder>    # add folder and its contents 
git add -p          # review changes and add files interactively
```
2. Commit changes with the message
```
git commit -m "<your-commit-message"  # commits all staged changes
git commit                            # open editor(notepad++) for typing commit message
```

### Stashing your work
The `git stash` command takes your uncommitted changes (both staged and unstaged), saves them away for later use, and then reverts them from your working copy
```
git stash                        # stashes staged changes
git stash save "<stash-message>"
git stash -u                     # stash staged files including untracked files
git stash list                   # list stashed changes
git stash show stash@{0}         # show stash details
git stash apply stash@{0}        # apply stash changes to working directory
```

### Inspecting a repository

- `git status` - List which files are staged, unstaged, and untracked
> The git status command displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven’t, and which files aren’t being tracked by Git.

- `git log` - Displays committed snapshots
> The git log command displays committed snapshots. It lets you list the project history, filter it, and search for specific changes.

-  `git log -n <limit>`
> Display the entire commit history using the default formatting. If the output takes up more than one screen, you can use Space to scroll and q to exit

- `git log --oneline`
> Condense each commit to a single line. This is useful for getting a high-level overview of the project history

### Undoing a committed snapshot
There are technically several different strategies to 'undo' a commit. The following examples will assume we have a commit history that looks like:
```
git log --oneline
872fa7e Try something crazy
a1e8fb5 Make some important changes to hello.txt
435b61d Create hello.txt
9773e52 Initial import
```
We will focus on undoing the 872fa7e Try something crazy commit. Maybe things got a little too crazy.


- `git reset --hard a1e8fb5 ` 

   Commit history is reset to that specified commit. Examining the commit history with `git log` will now look like
```
  git log --oneline
  a1e8fb5 Make some important changes to hello.txt
  435b61d Create hello.txt
  9773e52 Initial import
```

- `git commit --amend`

   In some cases though, you might not need to remove or reset the last commit. Maybe it was just made prematurely. In this case you can amend the most recent commit. Once you have made more changes in the working directory and staged them for commit by using `git add`, you can execute `git commit --amend`. This will have Git open the configured system editor and let you modify the last commit message. The new changes will be added to the amended commit.