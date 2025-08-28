For Day 25, The task was to merge branches where the difference between branches is the addition of new files (no merge conflict).

1. The first step is to repeat the actions done in [[Day 24 - Git Create Branches]] to create a new branch `nautilus` and then switch to it
2. Then, we create a new file to make the branches a bit different and we have to commit them.
```bash
git add new.txt
git commit -m "ADD: new file"
```
	
3. Lastly for merging, we switch back to the master branch and merge:
```bash
git checkout master
git merge nautilus
```
4. The actual last step includes pushing the code to remote/origin repo.
```bash
git push origin
```
## Resources
- My own git notes (will put the lank when Uploaded)