# Git Essentials

A very good reference that is thorough yet light is [https://www.atlassian.com/git/glossary#commands](https://www.atlassian.com/git/glossary#commands).

Git commands I use most frequently in my work.

### Clone a repo

```
git clone <repo_url>
```

### Rename a branch

```
git branch -M <new_name>
```

### Checkout a remote branch

```
git checkout -b <branch_name> <origin/branch_name>
```

### Clear git cache

```
git rm -r --cache .
```

### Delete local branch

```
git branch -D <branch_name>
```

### Delete remote branch

```
git push origin --delete <branch_name>
```

### List remote origin

```
git remote -v
```

### Change url of remote origin

```
git remote set-url origin git@github.com:User/UserRepo.git
```

### Delete remote origin

```
git remote remove origin
```

### Add a remote origin

```
git remote add origin <remote_url>
```

### Edit previous commit message

```
git commit --amend
```
 - opens up git editor.

### List checkouts one line

```
git log --pretty=oneline
```

### Go back to a previous commit

```
 git reset --soft HEAD~1
```
Reset will rewind your current HEAD branch to the specified revision. In our example above, we'd like to return to the one before the current revision - effectively making our last commit undone.

Note the --soft flag: this makes sure that the changes in undone revisions are preserved. After running the command, you'll find the changes as uncommitted local modifications in your working copy.

If you don't want to keep these changes, simply use the --hard flag. Be sure to only do this when you're sure you don't need these changes anymore.

### Go back to the previous commit (hard)

```
git reset --hard HEAD~1
```

### Go back to a particular commit

```
git reset --hard 0ad5a7a6
```

![Revert to a particular commit](../images/toolbox/revert-to-particular-commit.png)

<br>