In Day 26's task, we had to make and manage a remote repository. 

1. Checking the remotes available as a list (works without -v, too)
```bash
git remote -v
```
2. Create a remote and point to it's location (in this case it's local!)
```bash
git remote add dev_games /opt/xfusioncorp_games.git
```
3. Copy a file from the remote and commit changes
```bash
cp /tmp/index.html .
git add index.html
git commit -m "ADD:index file"
```
4. Push master branch to the new remote
```bash
git push dev_games master
```
## Resources
- [Git - Working with Remotes](https://git-scm.com/book/ms/v2/Git-Basics-Working-with-Remotes)