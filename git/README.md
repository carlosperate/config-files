# General git commands I might use

Good resource: [Flight rules for Git](https://github.com/k88hudson/git-flight-rules)


## Add local username and email

```
git config user.name "carlosperate"
git config user.email "carlosperate@users.noreply.github.com"
```

### Change the user and email from a commit

```
git commit --amend --no-edit --author="carlosperate <carlosperate@users.noreply.github.com>"
```


## Push as a different user

```
git push https://carlosperate@github.com/carlosperate/<repo>.git
```


## Rewrite history

!!! Warning - You know this is bad

See where to start rebasing from:

```
git log --graph --oneline
```

Copy the hash and insert in:

```
git rebase --interactive commit_hash^
```

The `^` is for the number of commits from that point you want to rebase.

On the opened file, find the commit you want and change `pick` to `edit`, save and close the file. You should get something along the lines of:

```
Stopped at <commit_hash>...  <commit_title>
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue
```

So, as indicated, edit the commit as you like:

```
git commit --amend
```

And finally:

```
git rebase --continue
```


## Undo git add

```
git reset <file>
```
