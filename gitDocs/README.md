## Git Docs

### Table of Contents

1. How to Initalize a git repo and connect it to github.
2. How to push (update) changes to github from local repo.
3. How to create the .gitignore file and update it to the github (Special Instructions)
4. How to pull (update) your git repo from github.
5. How to handle multiple branches.

### End of Table of Contents

---

### Chapter 1 - Initalize a git repo and connect it to github

```
git init
git add .
git commit -m "First Commit"
git remote add orgin <github link>
git push -u origin master
```

### End of Chapter 1

---

### Chapter 2 - How to push (update) changes to github from local repo

```
git add .
git commit -m "<Insert Personal Comments on your changes>"
git push origin <nameOfBranch>
```

or 

*** Warning The Second Method only adds changes with current files if created a new file the new file will not be added, please use the first method ***

```
git commit -am "<Insert Personal Comments on your changes>"
git push origin <nameOfBranch>
```

#### Side Note

```
git status = checks the status of the git branch
git log = shows all the git commits you have done in that past
```

### End of Chapter 2

---

### Chapter 3 - How to create the .gitignore file and update it to github

```
-> Go to your project folder
touch .gitignore
vim .gitignore
a // This will allow you to start editing in vim
<Insert .gitignore commands>
-> Hit ESCAPE
:w // This command saves your file in vim
:x // This command allows you to exit vim
-> Push to Github (See Chapter 2)
```

#### Special Steps

** WARNING** Only Continue to this step if you have already pushed to github

'''
This removes all the files from the github repo and adds them back in with the .gitignore file working correctly
'''

```
git rm -rf --cached .
git add .
-> Do Chapter 2 again to push everything back to github
```

#### Side Notes

```
*.DS_Store // Removes a useless mac file from ever being saved into your repo
```

Link to example .gitignore files = [Here](https://github.com/github/gitignore)

### End of Chapter 3

---

### Chapter 4 - How to pull (update) your local git repo from github

'''
When you need to update your local git repo with the main github repo
'''

```
git pull origin master
```

### End of Chapter 4

---

### Chapter 5. How to Handle Multiple Branches

'''
When you want to see what branches you have in your local repo (git)
'''

```
git branch
```

'''
When you want to create a new local (git) branch
'''

```
git branch <nameOfTheBranchYouWantToCreate>
```

'''
When you want to change from one git branch to another
'''

```
git checkout <nameOfBranchYouWantToEnter>
```

'''
When you want to push that second local (git) branch to a new github (remote) repo that you created just now
'''

```
git commit -am "<Insert Personal Comments on your changes>"
git push origin <nameOfLocal(git)Branch>
```

'''
When you want to push your second branch to another local branch
'''

```
git push <remote> <localBranch>:<remoteName>

example:

Two Branches:
-myFeature
-feature

You want to update the feature branch with the stuff from myFeature Branch

git push origin myFeature:feature
```

More Info on branches here 

- [dev Connected Tutorial](https://devconnected.com/how-to-push-git-branch-to-remote/)


More info coming later


### End of Chapter 5


---

#### Credits - Athanasios Karastogiannis
