
### My typical git (gitflow like) workflow
- List all local braches with the last commit info
```bash
git branch -v
```
- List all local and remote branches

- Switch between
```bash
git switch brach_name
```

- create a new branch from develop
```bash
git checkout -b feature/1234 develop
```
- Make some changes 
- Commit the changes (stage them locally)
```bash
git commit -a
```
- Set tracking info : local branch "feature/1234" to track remote branch "develop"
> needed for the next command
```
git branch --set-upstream-to=origin/develop feature/1234
```
- Rebase current branch on top of the upstream tracking brach 
> The upstream tracking branch will often diverge from your branch)
```bash
git pull --rebase
```
>it's helpful to run "git pull --rebase" almost everytime after every "git commit" to sync your current branch with remote changes

- Push changes from current local branch "feature/123" to uptream branch "feature/123"
>Will create a new branch with the same name if it doesn't exist
```bash
git push origin feature/1234
```
> The above creates a new upstream branch if it does not exist. Github will prompt you to create a PR

- Create a PR
- Merge the PR using the GH UI or You could also merge your branch using the git cli
```
# Remember Rebase current branch on top of the upstream 
# tracking branch so you don't miss any upstream changes
git pull --rebase
git merge --no-ff feature/123
git push
```
- Once a PR is merged, Cleanup: Delete the remote and local branches
```bash
git push origin --delete feature/1234
git branch -d feature/1234
```
