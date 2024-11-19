# Git-Github-Notes
### **Version Control System (VCS) - Notes with Example Commands**

---

### **What is a Version Control System (VCS)?**
A Version Control System is a tool that helps to track and manage changes to code or files over time. It allows multiple developers to work on the same project simultaneously, track changes, and manage different versions of files.

- **Benefits**:
  - Track changes and versions.
  - Collaborate among multiple developers.
  - Easily revert to previous versions.
  - Manage conflicts between changes.

### **Types of Version Control Systems:**

1. **Local Version Control:**
   - One-to-one interaction between a developer and the version control system.
   - **Example**: RCS (Revision Control System)
   - **Limitation**: Doesn’t support collaboration among multiple developers.

2. **Centralized Version Control System (CVCS):**
   - One central repository where all developers push and pull changes.
   - **Example**: CVS, Subversion (SVN), TFS (Team Foundation Version Control)
   - **Limitation**: If the central repository goes down, developers can’t work.

3. **Distributed Version Control System (DVCS):**
   - Every developer has a local copy of the repository, allowing them to work offline and later sync with the central repository.
   - **Example**: Git, Mercurial, BitKeeper
   - **Benefit**: No single point of failure, works offline, allows easy collaboration.

---

### **What is Git?**
Git is a distributed version control system (DVCS) that helps developers track changes to files and collaborate with others on projects. It is known for its speed, flexibility, and ability to handle large projects.

- **Key Concepts**:
  - **Working Directory**: Your actual project files on your computer.
  - **Staging Area (Index)**: A space where changes are prepared before being committed to the repository.
  - **Local Repository**: A hidden `.git` folder in the project directory that stores the history of commits.
  - **Remote Repository**: A central or cloud-based repository (e.g., GitHub, GitLab) where your code is shared.

### **Common Git Commands and Examples**

#### **1. Install Git (Linux)**
```bash
# Install Git on Linux (CentOS/RHEL)
sudo yum install git

# Verify Git Installation
git --version
```

#### **2. Initialize a Git Repository**
```bash
# Create a new directory and navigate to it
mkdir gitdemo
cd gitdemo

# Initialize a new Git repository in the current directory
git init

# Check the status of the repository
git status
```

#### **3. Create a File and Add it to Git**
```bash
# Create a new file using vim
vim file1.txt

# Check the status, Git will show the file as untracked
git status

# Add the file to the staging area
git add file1.txt

# Commit the file with a message
git commit -m "Added file1.txt"
```

#### **4. View Commit History**
```bash
# View detailed commit logs
git log

# View a summary of commits (one line per commit)
git log --oneline

# View changes for a specific commit using its commit ID
git show <commit-id>
```

#### **5. Modify and Commit Changes to an Existing File**
```bash
# Modify the file
vim file1.txt

# Check the status, Git will show the file as modified
git status

# Stage the changes
git add file1.txt

# Commit the changes
git commit -m "Modified file1.txt"
```

#### **6. Check Differences (Diff)**
```bash
# View changes that are not staged
git diff

# View changes that are staged for the next commit
git diff --staged
```

#### **7. Delete a File**
```bash
# Remove the file from the working directory and the repository
git rm file1.txt

# Commit the deletion
git commit -m "Deleted file1.txt"
```

#### **8. Ignore Files**
```bash
# Create a .gitignore file and add files/folders to ignore
vim .gitignore
# Add files to ignore, e.g., log files or temporary files
echo "log/*.log" >> .gitignore

# Check status, Git will ignore the specified files
git status
```

#### **9. Create and Manage Branches**
```bash
# Create a new branch named "feature-branch"
git branch feature-branch

# List all branches
git branch

# Switch to the new branch
git checkout feature-branch

# Verify you're on the correct branch
git status

# Create a new file in the new branch
vim feature-file.txt
git add feature-file.txt
git commit -m "Added feature-file.txt"
```

#### **10. Merge Branches**
```bash
# Switch to the branch you want to merge changes into (e.g., master)
git checkout master

# Merge the feature branch into master
git merge feature-branch

# If there are conflicts, manually resolve them, then:
git add <conflicted-files>
git commit -m "Resolved merge conflicts"
```

#### **11. Reverting Changes**
```bash
# Revert a commit by creating a new commit that undoes the changes
git revert <commit-id>
```

#### **12. Resetting Changes**
```bash
# Reset the repository to a specific commit (hard reset)
git reset --hard <commit-id>

# This will discard all changes after the specified commit
```

#### **13. Stashing Changes (Temporarily Saving Changes)**
```bash
# Stash uncommitted changes to return to a clean working directory
git stash

# View stashed changes
git stash list

# Apply the most recent stash
git stash pop

# Apply a specific stash without removing it from the stash list
git stash apply stash@{0}
```

#### **14. Working with Remote Repositories**
- **Clone a Repository**
```bash
# Clone a remote repository to your local machine
git clone https://github.com/username/repository.git
```

- **Adding a Remote Repository**
```bash
# Add a remote repository (e.g., GitHub) to your local Git repository
git remote add origin https://github.com/username/repository.git

# Verify the remote
git remote -v
```

- **Push Changes to Remote**
```bash
# Push local commits to the remote repository (usually on master or main branch)
git push origin master

# Push a specific branch to the remote repository
git push origin feature-branch
```

- **Pull Changes from Remote**
```bash
# Pull changes from the remote repository to update your local repository
git pull origin master
```

- **Fetch Changes from Remote**
```bash
# Fetch changes from the remote repository (without merging)
git fetch origin
```

#### **15. Deleting Branches**
```bash
# Delete a local branch
git branch -d feature-branch

# Delete a branch from the remote repository
git push origin --delete feature-branch
```

---

### **GitHub Integration**

#### **Create a New Repository on GitHub**
1. Go to GitHub and create a new repository.
2. Copy the repository URL.

#### **Connect Local Repository to GitHub**
```bash
# Add the remote GitHub repository URL
git remote add origin https://github.com/username/repository.git

# Verify the remote URL
git remote -v
```

#### **Push Local Repository to GitHub**
```bash
# Push local changes to GitHub (origin) on the master branch
git push origin master
```

#### **Pull from GitHub to Local Repository**
```bash
# Pull remote changes from GitHub to local repository
git pull origin master
```

---

### **Conclusion**
Git allows developers to track changes, work collaboratively, and manage code versions. Whether you're working solo or with a team, mastering Git is essential for efficient version control and code management. This guide covers the basics and common use cases, but Git has many more powerful features for advanced workflows and collaboration.

