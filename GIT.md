# GH - interactive authentication (easy)
Login into your **github.com** account 
```
gh auth login
```
Will provide a code and open a browser tab, paste code\
Now you can use git on that terminal


# Basic Setup
Install 
```
sudo apt-get update
sudo apt-get install git
```
Setup user
```
git config --global user.email my_email@gmail.com
git config --global user.name  my_github_username
```
If needed, reset all local user settings
```
git config --global --unset user.name
git config --global --unset user.email
git config --global --unset-all user.name
```

# Repos
Clone Repo
```
git clone https://github.com/<username>/REPO
cd REPO
```
Setup Token (password)
```
git remote remove origin
git remote add origin https://<token>@github.com/<username>/REPO.git
```

If you **don't have a token**, go to https://github.com/settings/tokens, click on "Generate a new token", copy/paste <token> **above**
    
Create a change and push it
```
touch file1.txt
git add --all
git commit -m "just a test"
git push -u origin master
```

Download latest changes from GitHub (if there were any) and merge
```
git fetch origin
git merge origin/master
```

Add only selected folders/files only, commit and push:
```
git add data00/*
git add data02/*
git add data04/*
git add data05/*
git add data06/*
git commit -m "data folders"
git push -u origin master
```

Download all changes done on the GITHUB page to keep local copy on sync
```
git pull origin master
```

If ERROR: Your local changes to the following files would be overwritten by merge:... SOLUTION:
```
git reset --hard
git pull origin master
```

Remove delete a file from REPO
```
rm data-folder.zip
git commit -a -m "deleted data zip file"
git push origin master
```

# Branches

Check what branch you are in (typically the master branch)
```
git branch
```

You’re going to work on issue #66 in whatever issue-tracking system your company uses
```
git branch   branch66
git checkout branch66
```

Both commands at the same time
```
git checkout -b branch66
```

Check what branch you are on now
```
git branch
```

Make changes, add, commit, push
```
touch file2.txt
git add -all
git commit -m "changes"
git push -u origin branch66
```

See remote changes and switch to a different branch
```
git fetch origin
git branch -a
```

Will show all new remote branches (ex. remotes/origin/branch88). Switch to it:
```
git checkout branch88
git branch    
```

Fetching changes from a remote repository: to retrieve new work done by other people. Fetching from a repository grabs all the new remote-tracking branches and tags without merging those changes into your own branches.

If you already have a local repository with a remote URL set up for the desired project, you can grab all the new information by using git fetch *remotename* in the terminal:
```
git fetch remotename
```

Merging changes into your local branch: combines your local changes with changes made by others
* Typically, you'd merge a remote-tracking branch (i.e., a branch fetched from a remote repository) with your local branch:
```
git merge remotename/branchname
```
This merges updates made online with your local work

    
git pull is a convenient shortcut for completing both git fetch and git merge in the same command:
```
git pull remotename branchname
```
# Clone a specific branch
```
git clone -b <branch> <remote_repo>
git clone -b dev1 https://github.com/andrespgd/Python
```

# Create a new local branch and push it to GitHub
```
git clone https://github.com/andrespgd/Python
cd Python
git branch dev10
git checkout dev10
touch new_script.py
git add new_script.py
git commit -m "new script"
git push origin dev10
```
will show in GitHub Repo as new branch, but it has no pull request yet
```
git push origin dev10:master
```
will automatically apply the changes to the master in Github
    
# Other

Ignore files
* Ex.ignore a file called readme.txt, write readme.txt in the .gitignore file.
* by name of the extension: write *.txt
* by whole folder,just write test/ in the file


## Shallow Clone
    If you are in a hurry or have a slow connection, will clone ONLY the most recent commit, rather than the entire history
```
git clone --depth 1 https://www.github.com/...........git
```

## Git Fetch Vs. Pull
```
https://www.youtube.com/watch?v=GOrhB6eYASU
```
