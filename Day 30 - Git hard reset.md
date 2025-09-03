In this task we have to return the working tree to an older version of it and reset it to a certain commit.

1. To check if you pushed your code to remotes or note
```bash
git log --oneline --branches --not --remotes
```
2. Getting the commit hash
```bash
git log --oneline | grep "add data.txt"
```
3. After that, we reset to that commit
```bash
git reset --hard <commit-hash>
```
4. push to origin
```bash
git push --force origin master
```


## Resources
- [Undo a git commit - git reset/revert - pushed/not pushed](https://www.youtube.com/watch?v=GytsxgB4-HU)
- [8. Git Tutorial - Undo things using git reset](https://www.youtube.com/watch?v=OGk5rvYw8c0)
- https://youtube.com/shorts/rZbBUC40kHU?si=k_UPo7TF6pCLSXTk