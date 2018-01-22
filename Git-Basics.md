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

