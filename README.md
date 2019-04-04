# git-notes

#### copy commits from repo A to repo B
```
cd repoA
git remote rename origin origin2
git remote add origin https://github.com/username/repoB.git
git fetch --depth=(number of commits) origin2 master
git push -u origin master --force
```
#### delete a file from git history
```
git filter-branch --index-filter "git rm -rf --cached --ignore-unmatch PATH_TO_FILE" HEAD
```
