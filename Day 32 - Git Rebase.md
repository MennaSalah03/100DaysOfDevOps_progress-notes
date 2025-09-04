Today's task was to use rebasing instead of merging using `git merge`. The difference between them is that rebase is actually more convenient. Unlike merging, the git history becomes more linear and the merge conflicts are minimized. The rebased branch also maintains all the main/master changes,

1. Make sure the branch is correct (feature) 
```
git status
```
2. Rebase to master
```
git rebase master
```
3. push the changes
```
git push --force origin feature
```

## Resources
- [git rebase - Why, When & How to fix conflicts - YouTube](https://www.youtube.com/watch?v=DkWDHzmMvyg)
- [git rebase](https://www.youtube.com/watch?v=Tz6J-oYO-Xo)
- [What's the difference between 'git merge' and 'git rebase'? - Stack Overflow](https://stackoverflow.com/questions/16666089/whats-the-difference-between-git-merge-and-git-rebase/16666418#16666418)
- [Git - git-rebase Documentation](https://git-scm.com/docs/git-rebase)
