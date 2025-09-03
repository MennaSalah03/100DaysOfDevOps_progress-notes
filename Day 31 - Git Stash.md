In this task, we have an already made stash and we're supposed to get one of them onto the working tree 

1. See the list of stashes
```
git stash list
```
2. Restore stash `stash@{1}`
```
git stash pop stash@{1}
```
stash pop by default restores the top of the stack of stashes, so we specified the specific stash we wanted.
3. commit and push to origin
```
git commit -m "Added welcome file"
git push origin master
```

## Resources
- [Git - git-stash Documentation](https://git-scm.com/docs/git-stash)
- [Git STASH Tutorial](https://www.youtube.com/watch?v=BSLzA8oCT7g)
- [[Arabic] Learn Git & GitHub #13 - Mastering Stash Part 1](https://www.youtube.com/watch?v=PL4vYFEiXas)
- [[Arabic] Learn Git & GitHub #14 - Mastering Stash Part 2](https://www.youtube.com/watch?v=FsiF4fpy14I)