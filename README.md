# Basic Git Practice

Objective: Create a local Git repository and commit a file.

```
# Check Git version
git --version

# Configure Git
git config --global user.name "Student"
git config --global user.email "student@example.com"

# Create project
mkdir devops-demo
cd devops-demo

# Initialize Git repository
git init

# Create file
echo "Welcome to DevOps" > README.md

# Check status
git status

# Stage changes
git add README.md

# Commit changes
git commit -m "Initial commit"

# View history
git log --oneline
```

- Assignment : Install Git, create a repository, and make your first commit.

# Version Control Systems (VCS) and Git

## 1. Brief History of Version Control Systems

Definition: A Version Control System (VCS) is a tool used to track, manage, and maintain changes to files and source code over time.

| Year | Technology | Significance                         |
| ---- | ---------- | ------------------------------------ |
| 1972 | SCCS       | Early source code version control    |
| 1982 | RCS        | File revision management             |
| 1986 | CVS        | Centralized version control          |
| 2000 | SVN        | Improved centralized version control |
| 2005 | Git        | Distributed version control          |
| 2008 | GitHub     | Cloud-based Git repository hosting   |

### Types of Version Control

| Type            | Description                             | Example        |
| --------------- | --------------------------------------- | -------------- |
| Local VCS       | Stores versions locally                 | RCS            |
| Centralized VCS | Uses a central server                   | SVN, CVS       |
| Distributed VCS | Every clone contains repository history | Git, Mercurial |

## 2. Introduction to Git

Definition: Git is a free, open-source, distributed version control system developed by Linus Torvalds in 2005.

### Key Features

- Distributed version control.
- Tracks source code changes.
- Supports branching and merging.
- Enables team collaboration.
- Maintains commit history.
- Supports offline development.
- Integrates with CI/CD pipelines.

### Important Git Terminology

| Term       | Definition                             |
| ---------- | -------------------------------------- |
| Repository | Storage for project files and history  |
| Commit     | Snapshot of tracked changes            |
| Branch     | Independent line of development        |
| Merge      | Combines changes from branches         |
| Clone      | Copies a remote repository             |
| Push       | Uploads commits to a remote repository |
| Pull       | Fetches and integrates remote changes  |

## 3. Need for Version Control

### Why Version Control Is Important

1. Track changes in source code.
2. Restore previous versions.
3. Support multiple developers.
4. Prevent accidental loss of work.
5. Manage different development branches.
6. Maintain project history.
7. Support DevOps and CI/CD automation.

### Without Git vs With Git

| Without Git                  | With Git                  |
| ---------------------------- | ------------------------- |
| Manual file backups          | Automated version history |
| Difficult collaboration      | Easy team collaboration   |
| No structured change history | Complete commit history   |
| Difficult rollback           | Restore previous versions |
| Manual code integration      | Branching and merging     |

## 4. Evolution of Git

- 2005: Linus Torvalds created Git for Linux kernel development.
- 2008: GitHub launched, simplifying Git collaboration.
- 2010s: Git became widely adopted in software development.
- Today: Git is a core tool in DevOps, CI/CD, and Infrastructure as Code workflows.

### Git Architecture

Working Directory

Staging Area

Local Repository

git add →

git commit →

git push →

Remote Repository (GitHub)

## 5. Basic Git Commands — Practice

```
# Check Git version
git --version

# Configure Git
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Create repository
mkdir git-practice
cd git-practice
git init

# Create a file
echo "Hello Git" > index.html

# Check status
git status

# Stage changes
git add index.html

# Commit changes
git commit -m "Initial commit"

# View history
git log --oneline
```

## 6. Points to Remember

- Git is a VCS; GitHub is a Git hosting platform.
- Git was created in 2005.
- Git is distributed, while SVN is centralized.
- `git add` stages changes.
- `git commit` records changes locally.
- `git push` uploads commits to a remote repository.
- Git is widely used in DevOps and CI/CD.

## 7. Practical Assignment

Task: Create a Git repository and track file changes.

1. Install Git.
2. Configure username and email.
3. Create a local repository.
4. Create `index.html`.
5. Make the first commit.
6. Modify the file and create a second commit.
7. Display commit history using `git log --oneline`.

Expected Outcome: Students understand Git history, repository initialization, staging, commits, and basic version tracking.


## Version Control and Git

Version Control: Tracks and manages changes to files.

Git: Distributed Version Control System created by Linus Torvalds in 2005.

GitHub: Cloud platform for hosting and collaborating on Git repositories.

### Points to Remember

- Local VCS: RCS
- Centralized VCS: SVN
- Distributed VCS: Git
- Git works offline.
- GitHub hosts remote repositories.
- Git Workflow: Working Directory → Staging Area → Local Repository → Remote Repository

## 3. Git Installation and Configuration

### Installation

```
# Windows (PowerShell)
winget install --id Git.Git -e

# Ubuntu
sudo apt update
sudo apt install git -y

# RHEL / Amazon Linux 2023
sudo dnf install git -y

# macOS
brew install git

# Verify
git --version
```

### Initial Configuration

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --list
```

## 4. Git Basic Commands – Practice

```
# Create repository
mkdir git-practice
cd git-practice
git init -b main

# Create file
echo "Hello DevOps" > index.html

# Check status
git status

# Stage changes
git add .

# Commit changes
git commit -m "Initial commit"

# Modify file
echo "Git Practice" >> index.html

# View changes
git diff

# Commit changes
git add .
git commit -m "Updated index"

# View history
git log --oneline
```

### Important Commands

| Command               | Purpose               |
| --------------------- | --------------------- |
| `git init`            | Initialize repository |
| `git status`          | Check status          |
| `git add .`           | Stage changes         |
| `git commit -m "msg"` | Commit changes        |
| `git log --oneline`   | View history          |
| `git diff`            | Compare changes       |
| `git show`            | Show commit details   |

## 5. GitHub – Remote Repository

### Practice

1. Create a GitHub account.
2. Create an empty repository named `git-practice`.
3. Connect the local repository.
4. Push code to GitHub.
5. Clone and pull changes.

```
# Connect GitHub
git remote add origin https://github.com/USERNAME/git-practice.git

# Verify remote
git remote -v

# Push code
git push -u origin main

# Clone repository (outside existing project)
git clone https://github.com/USERNAME/git-practice.git

# Pull changes
git pull origin main

# Push changes
git push origin main
```

Remember: `fetch` downloads updates, `pull` downloads and integrates changes, and `push` uploads commits.

## 6. Git Branching and Merge

Branch: Independent line of development.

Merge: Integrates changes from another branch.

### Practice

```
# Create branch
git switch -c feature

# Create file
echo "Feature Code" > feature.txt

# Commit
git add .
git commit -m "Added feature"

# Switch to main
git switch main

# Merge branch
git merge feature

# List branches
git branch -a

# Delete merged branch
git branch -d feature
```

## 7. Git Rebase and Cherry-Pick

Rebase: Replays commits onto another base, creating new commit IDs.

Cherry-Pick: Applies changes from a selected commit to the current branch.

```
# Rebase feature branch
git switch feature
git rebase main

# Cherry-pick selected commit
git switch main
git cherry-pick <commit-hash>

# View history
git log --oneline --graph --all
```

| Merge                  | Rebase                    | Cherry-Pick                    |
| ---------------------- | ------------------------- | ------------------------------ |
| Integrates branches    | Replays commits           | Copies selected commit changes |
| Preserves ancestry     | Rewrites replayed commits | Creates new commit             |
| Good for collaboration | Good for local cleanup    | Good for specific fixes        |

## 8. Git Merge Conflict

Definition: Conflict occurs when Git cannot automatically combine changes.

### Practice

```
# Create branch
git switch -c feature-test

# Modify same line in a file
echo "Feature Change" > index.html
git add .
git commit -m "Feature update"

# Modify on main
git switch main
echo "Main Change" > index.html
git add .
git commit -m "Main update"

# Merge (conflict expected)
git merge feature-test
```

Resolution:

```
# Edit file to desired content
echo "Resolved Content" > index.html

git add index.html
git commit -m "Resolved conflict"
git status
```

Remember: `git merge --abort` cancels an in-progress conflicted merge.

## 9. Git Stash

Definition: Temporarily saves uncommitted changes.

```
# Modify tracked file
echo "Temporary Work" >> index.html

# Save changes
git stash

# List stash
git stash list

# Apply stash
git stash apply

# Save changes again
git stash

# Restore and remove latest stash
git stash pop
```

Remember: `apply` keeps the stash entry; `pop` removes it after successful application.

## 10. Git Rollback – Reset, Revert, Restore

### Git Reset

Definition: Moves HEAD and optionally resets staged and working changes.

```
# Keep changes staged
git reset --soft HEAD~1

# Keep changes unstaged
git reset --mixed HEAD~1

# Discard tracked changes
git reset --hard HEAD~1
```

### Git Revert

Definition: Creates a new commit reversing an earlier commit.

```
git revert HEAD
```

### Git Restore

Definition: Restores files or unstages changes.

```
# Discard unstaged changes
git restore index.html

# Unstage file
git restore --staged index.html
```

### Comparison

| Command         | Use Case                          |
| --------------- | --------------------------------- |
| `reset --soft`  | Undo commit, keep staged changes  |
| `reset --mixed` | Undo commit, keep working changes |
| `reset --hard`  | Discard local tracked changes     |
| `revert`        | Safely undo a committed change    |
| `restore`       | Restore or unstage files          |

Warning: Practice `reset --hard` only in a disposable repository. Prefer `revert` for shared commits.

## 11. Git Best Practices

- Use meaningful commit messages.
- Create feature branches.
- Commit small, logical changes.
- Use `.gitignore`.
- Never commit passwords or secrets.
- Review code using pull requests.
- Avoid force-pushing shared branches.
- Use `git revert` for undoing pushed commits.

## 12. Training Assignments

| No. | Assignment                       | Expected Result        |
| --- | -------------------------------- | ---------------------- |
| 1   | Install and configure Git        | Git configured         |
| 2   | Create repository with 5 commits | Commit history         |
| 3   | Push repository to GitHub        | Remote repository      |
| 4   | Clone, pull and push             | Synchronized code      |
| 5   | Create and merge 2 branches      | Merged code            |
| 6   | Practice rebase and cherry-pick  | Updated history        |
| 7   | Generate and resolve conflict    | Successful merge       |
| 8   | Practice stash and pop           | Restored changes       |
| 9   | Practice reset, revert, restore  | Rollback demonstration |

## 13. Final Practical Assignment

Project: `git-devops-practice`

Objective: Demonstrate Git and GitHub collaboration.

Tasks:

1. Create a GitHub repository.
2. Add `index.html`, `app.py`, and `README.md`.
3. Make 5 commits.
4. Create `feature-login` and `feature-dashboard`.
5. Merge both branches.
6. Resolve one merge conflict.
7. Practice rebase and cherry-pick.
8. Demonstrate stash.
9. Practice reset, revert, and restore.
10. Push final code to GitHub.

Deliverable: GitHub repository link, commit history, branch history, and completed assignments.

Training Outcome: Learners can manage Git repositories, collaborate through GitHub, work with branches, resolve conflicts, and perform safe rollback operations.
