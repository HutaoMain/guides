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
