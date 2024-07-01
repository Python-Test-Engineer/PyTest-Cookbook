# Git Essentials

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

### Go back to a previous checkout

### Go back to a previous checkout (hard)


<br>