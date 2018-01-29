In Terminal

```bash
mkdir ~/.bash
```

Copy the raw `git-prompt.sh` file from git contrib in to the `~/.bash` directory: https://github.com/git/git/blob/master/contrib/completion/git-prompt.sh

Inside `~/.bashrc` or `~/.bash_profile` (choose the file where you normally put any bash customizations/setup), add the lines:

```bash
source ~/.bash/git-prompt.sh # Show git branch name at command prompt
export GIT_PS1_SHOWCOLORHINTS=true # Option for git-prompt.sh to show branch name in color

# Terminal Prompt:
# Include git branch, use PROMPT_COMMAND (not PS1) to get color output (see git-prompt.sh for more)
export PROMPT_COMMAND='__git_ps1 "\w" "\n\\\$ "' # Git branch (relies on git-prompt.sh)
```

As long as you're inside a git repo, your Bash prompt should now show the current git branch in color signifying if its got uncommitted changes.