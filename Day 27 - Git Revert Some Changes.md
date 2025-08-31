The task is to revert the tree to a certain commit (the most recent) that is ( HEAD ). 

1. To revert:
```bash
git revert HEAD --no-edit
```
2. committing the change
```bash
git commit --amend -m "revert beta"
```
3. To check the commits were done we can check the logs or the status
```bash
git log --oneline
git status
```
## Resources
- [Git - git-revert Documentation](https://git-scm.com/docs/git-revert)
- My own git notes (will add link when uploaded)