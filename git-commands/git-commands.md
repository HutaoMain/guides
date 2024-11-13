## GIT COMMANDS

### To delete local branch:

With confirmation:

```bash
git branch -d [branch-name]
```

Without confirmation:

```bash
git branch -D [branch-name]
```

### To delete remote branch:

```bash
git push origin :[branch-name]
```

### How to Undo a Pushed Git Commit - Reset a Git Commit After Push:

To see the logs with their commit hash

```bash
git log --oneline
```

```bash
git reset --hard [commit-hash]
```

```bash
git push --force
```

### How to undo local commit:

```bash
git reset HEAD~
```

## OR, reset to a specific commit before the one you want to undo:

```bash
git reset [commit-hash-before-the-commit-you-want-to-reset]
```

### How to remove unwanted commit in the middle: Note: this will change the commit hash of the upper part from the commit you remove to the latest commit:

```bash
git rebase -i [commit-hash-before-unwanted-commits]
```

In the list that opens, change pick to drop next to the unwanted commit(s).

Save and close the editor (escape :wq in Vim, Ctrl+S then close in VS Code).

After the rebase, force push the branch to update the remote:

```bash
git push origin [branch-name] --force
```
