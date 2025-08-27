This task is the first in Git tasks. We have to install Git on the storage server, and make a bare repository called `blog.git` in a directory `/opt/`. repos ending in `.git` is a bare repository

A bare repository doesn't have a working directory, so git commands won't work.

To install Git
```bash
yum install -y git
```

Creating bare repo.
```bash
cd /opt
git init  --bare blog.git
```
## Resources
- [Quickly create a Git bare repo with init or clone example](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/Quickly-create-a-git-bare-repo-with-init-or-clone)
- My own old git notes (will add a link when I upload them)