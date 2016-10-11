### View the current status of your files:
```Git status ```

* Green files are staged to be committed
* Red files are unstaged and will not be committed

#### Adding and Removing files

**To add certain files to be tracked:**  
```Git add <your file name>```

**You can also use wildcards:**  
```Git add "*.sql" ```

**This will add all of the changes**  
```Git add .```

**This will add all of the tracked changes to the repository**  
```Git add -u```

**Removing or deleting files from being tracked (this won't necessarily delete the file)**  
```Git rm <file name>```

### Committing and pushing changes

**Commit your changes to your local repo**  
```Git commit```

This will open VIM to add commit notes. To save your notes use the command wq

**Commit your changes with notes inline**  
```Git commit -m "Update the readme file"```

**When you messed up your commit message:**  
```Git commit --amend```

**Checks all changes from github and merges them into your local repo**  
```Git pull```

**Commits the change to the main repro**  
```Git push```

### Working with branches
**See local branches**  
```git branch```

**See local and remote branches**  
```git branch --all```

**Checkout branch**  
```git checkout <branch name>```

**Create a new branch and automatically navigate (checkout) that branch**  
```git checkout -b <branch name>```

_Once you have completed your work on your new branch you will add the changes and commit them like normal_  
```git add .```  
```git commit```

_**When you create a branch it will only be create locally - if you want that branch to also exist in your remote repository (origin) you will need to set an upstream path for it. When you push your commit you can use -u to set the upstream path.**_  

**Push your changes and setup the upstream path to your remote repository**  
```git push -u origin <branch name>```


### Merging changes

**Merging your branch into the master**  

1. Checkout the master branch  
```git checkout master```

2. Merge your change with the master branch  
```Git merge <your branch>```

3. Push the merged branch to the remote repository  
```Git push origin```

**Fixing merge conflicts**  

1. Run the merge tool - _there are many tools available for this I use Beyond Compare but there are other options available_  
```Git mergetool```
	
2. Make the changes to fix merge conflict
	
3. After fixing your conflicts you will need to commit your changes  
```Git commit -m "<any change notes about fixing the conflict>"```

**If things go really wrong you can abort the merge**  
```Git merge --abort```

### What to do when you screw up

**When you haven't staged or committed anything, or have staged only changes you no longer want:**  
```Git reset --hard (HEAD is default) # This will delete your changes```

**To unstage your commits**  
```Git reset HEAD~1```

**When you have already committed but haven't pushed:**  
```Git reset --hard origin/{branchname}```

**When you have already committed and pushed a bad commit:**  
```Git revert {SHA1}```  
```Git commit```  
```Git push origin```  

**Discard all local changes and get remote changes**  
```git fetch```  
```git reset --hard origin/master```  
