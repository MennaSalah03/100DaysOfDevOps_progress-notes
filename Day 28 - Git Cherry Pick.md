There are two branches in this repository, `master` and `feature`. For this task, we have merge one of the commits from the `feature` branch to the `master` branch, the message for the commit that needs to be merged into `master` is `Update info.txt`.

---
1. First of all, it's useful to get the hash of the commit we "cherry-pick"
```bash
git log --oneline feature | grep "Update info.txt"
```
2. Then, we need to switch to the master branch if we're not on it.
```bash
git checkout master
```
3. Now, we can cherry-pick the commit
```bash
   git cherry-pick <commit_hash>
```
4. Finally we push to the origin
```
git push origin master
```

## Resources
- [Git - git-cherry-pick Documentation](https://git-scm.com/docs/git-cherry-pick)
- [What is git cherry pick? - YouTube](https://www.youtube.com/watch?v=Q3Hg6PIghws)
- [Resolve Git Cherry Pick Merge Conflicts](https://www.youtube.com/watch?v=aUeNbpSkY8k)