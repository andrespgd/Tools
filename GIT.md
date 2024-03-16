# GH - interactive authentication (easy)
```
gh auth login
```
- gh command NEEDS TO BE INSTALLED FROM https://cli.github.com/
- terminal will ask a couple of questions
- will open a browser with GitHub page to login
- browser will ask for usn/pwd
- terminal Will provide a code
- enter it in browser
- now that terminal can run git commands to GitHub
- terminal will stay authenticated even after rebooting


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

Create new branch and switch to it
```
git branch   branch88
git checkout branch88
```

Both commands at the same time
```
git checkout -b branch88
```

Make changes, add, commit, push
```
touch file.txt
git add -all
git commit -m "changes"
git push -u origin branch88
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

Merging changes into your local branch
* combines your local changes with changes made by others
* Typically, you'd merge a remote-tracking branch with your local branch
* i.e., a branch fetched from a remote repository
```
git merge remotename/branchname
```
This merges updates made online with your local work

    
PULL: git fetch + git merge in the same command
```
git pull remotename branchname
```

# Clone a specific branch
```
git clone -b <branch> <remote_repo>
git clone -b dev1 https://github.com/andrespgd/Python
```

# Create a new local branch (and push to GitHub in 2 ways)
```
git clone https://github.com/andrespgd/Python
cd Python
git branch dev10
git checkout dev10
```
File: create/add/commit
```
touch new_script.py
git add new_script.py
git commit -m "new script"
```
Push Type#1 - will create a new branch in GitHub
```
git push origin dev10
```
Push Type#2 - will push/apply the changes into the master branch in GitHub
```
git push origin dev10:master
```
    
# Other

Ignore files
* .gitignore file
* ex. by filename readme.txt
* ex. by extension *.txt
* ex. by whole folder, just write folder_to_ignore/


## Shallow Clone
    If you are in a hurry or have a slow connection, will clone ONLY the most recent commit, rather than the entire history
```
git clone --depth 1 https://www.github.com/...........git
```

## Git Fetch Vs. Pull
```
https://www.youtube.com/watch?v=GOrhB6eYASU
```
