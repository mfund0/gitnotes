# gitnotes
```bash
A collection of my git learnings
```
### My typical git workflow
List all local braches with the last commit info
```bash
git branch -v
```
List all local and remote branches

Switch between
```bash
git switch brach_name
```

create a new branch from develop
```bash
git checkout -b feature/9803-private-ep develop
```
Make some changes 
Commit the changes (stage them locally)
```bash
git commit -a
```
Set tracking info : local branch "feature/1234" to track remote branch "develop"
> needed for the next command
```
git branch --set-upstream-to=origin/develop feature/1234
```
Rebase current branch on top of the upstream tracking brach 
> The upstream tracking branch will often diverge from your branch)
```bash
git pull --rebase
```
it's helpful to run "git pull --rebase" almost everytime after every "git commit" to sync your current branch with remote changes

Push changes from current local branch "feature/123" to uptream branch "feature/123"
>Will create a new branch with the same name if it doesn't exist
```bash
git push origin feature/1234
```

Create a PR
Once a PR is merged, Cleanup: Delete the remote and local branches
```bash
git push origin --delete feature/1234
git branch -d feature/1234
```
