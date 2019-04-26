# git-notes

#### copy commits from repo A to repo B
```
cd repoA
git remote rename origin origin2
git remote add origin https://github.com/username/repoB.git

#Copy master branch only
git fetch --depth=(number of commits) origin2 master
git push -u origin master --force

#Copy all branches
for remote in $(git branch -r); do git checkout ${remote##origin2/}; git fetch --depth=400 origin2 ${remote##origin2/}; git push -u origin ${remote##origin2/} --force; done
```

#### delete a file from git history
```
git filter-branch --index-filter "git rm -rf --cached --ignore-unmatch PATH_TO_FILE" HEAD
```
