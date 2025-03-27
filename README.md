# 📝 Git Cheat Sheet




## 1️⃣ Basic Setup
```bash

git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main

```
👉 Sets up Git with your name, email, and default branch.

________________________________________________________________

## 2️⃣ Initialize & Clone
```bash
git init                      # Initialize a new Git repo  
git clone <repo-url>          # Clone an existing repo  
git clone git@github.com:user/repo.git  # Clone via SSH

```
________________________________________________________________

## 3️⃣ Staging & Committing

```bash
git status                    # Check status  
git add .                     # Stage all changes
git diff                      # Lists out the changes between your current working directory/file and your staging area.
git commit -m "Commit message"  # Commit changes  
git commit --amend -m "New message"  # Edit last commit message  

```
________________________________________________________________
## 4️⃣ Branching


```bash
git branch                     # List branches  
git branch <branch-name>        # Create a new branch  
git checkout <branch-name>      # Switch branch  
git checkout -b <branch-name>   # Create and switch to a branch  
git merge <branch-name>         # Merge a branch into the current branch  
git branch -d <branch-name>     # Delete a branch  

```

________________________________________________________________

## 5️⃣ Working with Remote Repositories

```bash
git remote -v                  # List remote repositories  
git remote add origin <repo-url>  # Add a remote repo  
git push -u origin main        # Push code to GitHub  
git pull origin main           # Pull latest changes  
git fetch                      # Fetch changes without merging  

```

________________________________________________________________

## 6️⃣ Undoing Changes


```bash
git restore <file>             # To discard accidental changes made to the file (unstaged file)
git reset --soft HEAD~1        # Undo last commit (keep changes staged)  
git reset --hard HEAD~1        # Undo last commit and remove changes   
git checkout -- <file>         # Undo changes to a file  

```
________________________________________________________________
## 7️⃣ SSH vs HTTPS (For GitHub Authentication)


```bash
# Set up SSH for multiple accounts
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
ssh-add ~/.ssh/id_rsa_github

# Switch remote URL from HTTPS to SSH
git remote set-url origin git@github.com:user/repo.git

```
________________________________________________________________

## 8️⃣ Stashing (Temporary Storage of Changes)


```bash
git stash                      # Stash uncommitted changes  
git stash list                 # View saved stashes  
git stash apply                # Reapply the latest stash  
git stash drop                 # Delete the latest stash  
git stash pop                  # Apply and remove the stash  

```

________________________________________________________________

## 9️⃣ Logs & History

```bash
git log                        # View commit history  
git log --oneline --graph      # Compact log with a graph  
git blame <file>               # Show who modified each line
git diff --staged              # Displays the difference/changes between your current working directory/file(staged) and your previous commit

```
________________________________________________________________

## 🔄 Fixing Common Issues
❌ 403 Error: Password authentication removed?

👉 Use a Personal Access Token (PAT) instead of a password.


```bash
git credential reject https://github.com
git push -u origin main  # Enter PAT when prompted

```
________________________________________________________________

❌ Wrong credentials being used?

👉 Remove stored credentials and retry:
```bash
git credential reject https://github.com
git config --global credential.helper store

```


________________________________________________________________

❌ Merge conflicts?

👉 Manually edit the file, then:
```bash
git add .
git commit -m "Resolved merge conflict"

```

________________________________________________________________
