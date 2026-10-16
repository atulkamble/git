# Git and GitHub – Training Notes

Topics: Version Control Systems, Git Fundamentals, Git Commands, GitHub, Branching, Rebase, Merge, Cherry-Pick, Conflict Resolution, Stashing, and Rollback Techniques.

## 1. Basics of Git and Version Control Systems

### Definitions

| Topic                        | Definition                                                              |
| ---------------------------- | ----------------------------------------------------------------------- |
| Version Control System (VCS) | Tracks and manages changes to files over time.                          |
| Git                          | Distributed version control system developed by Linus Torvalds in 2005. |
| GitHub                       | Cloud platform for hosting and collaborating on Git repositories.       |
| Centralized VCS              | Stores project history on a central server.                             |
| Distributed VCS              | Each clone contains repository history.                                 |

### Brief History and Evolution

| Year | Technology | Significance                |
| ---- | ---------- | --------------------------- |
| 1972 | SCCS       | Early version control       |
| 1982 | RCS        | File revision management    |
| 1986 | CVS        | Centralized version control |
| 2000 | SVN        | Improved centralized VCS    |
| 2005 | Git        | Distributed version control |
| 2008 | GitHub     | Git repository hosting      |

### Need for Version Control

- Track source code changes.
- Maintain commit history.
- Restore previous versions.
- Support team collaboration.
- Manage multiple development branches.
- Integrate with DevOps and CI/CD pipelines.

### Git Workflow

Working Directory

Modify project files

git add

Staging Area

Prepare changes

git commit

Local Repository

Store commit history

git push

Remote Repository (GitHub)

Share and collaborate

## 2. Git Installation and Initial Setup

### Installation Commands

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

# Verify installation
git --version
```

### Initial Configuration

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --list
```

## 3. Git Fundamentals and Basic Commands

### Important Terminology

| Term       | Definition                     |
| ---------- | ------------------------------ |
| Repository | Project files and Git history  |
| Commit     | Snapshot of tracked changes    |
| Branch     | Independent development line   |
| HEAD       | Reference to current checkout  |
| Clone      | Copy of remote repository      |
| Merge      | Integrates branch changes      |
| Push       | Uploads commits                |
| Pull       | Fetches and integrates changes |

### Practical – Create a Git Repository

```
# Create project
mkdir git-practice
cd git-practice

# Initialize repository
git init -b main

# Create file
echo "Hello DevOps" > index.html

# Check status
git status

# Stage and commit
git add .
git commit -m "Initial commit"

# Modify file
echo "Git Practice" >> index.html

# View changes
git diff

# Second commit
git add .
git commit -m "Updated index"

# View history
git log --oneline
```

### Basic Git Commands

| Command               | Purpose                |
| --------------------- | ---------------------- |
| `git init`            | Initialize repository  |
| `git status`          | Check working state    |
| `git add .`           | Stage changes          |
| `git commit -m "msg"` | Create commit          |
| `git log --oneline`   | View commit history    |
| `git diff`            | View unstaged changes  |
| `git show`            | Display commit details |

## 4. Introduction to GitHub and Remote Repository

GitHub: A platform for storing Git repositories, collaboration, pull requests, and CI/CD integration.

### GitHub Account Setup

1. Visit [github.com](https://github.com?utm_source=chatgpt.com).
2. Create an account and verify your email.
3. Create a repository named `git-practice` without initializing files.
4. Connect the existing local repository.

### Practical – Connect, Push, Pull and Clone

```
# Connect local repository
git remote add origin https://github.com/USERNAME/git-practice.git

# Verify remote
git remote -v

# Push to GitHub
git push -u origin main

# Pull changes
git pull origin main

# Push updates
git push origin main

# Clone repository (from parent directory)
git clone https://github.com/USERNAME/git-practice.git
```

Points to Remember: `git fetch` downloads remote updates, `git pull` fetches and integrates them, and `git push` uploads commits. GitHub HTTPS authentication uses a token or credential manager rather than an account password.

## 5. Git Branching, Merge, Rebase and Cherry-Pick

### Git Branches

Definition: A branch provides an independent line of development.

```
# Create and switch branch
git switch -c feature

# Create feature
echo "Feature Code" > feature.txt

# Commit changes
git add .
git commit -m "Added feature"

# Switch to main
git switch main

# Merge feature
git merge feature

# List branches
git branch -a

# Delete merged branch
git branch -d feature
```

### Git Rebase

Definition: Replays commits on another base, rewriting their commit IDs.

```
# Run before merging feature
git switch feature
git rebase main
```

### Git Cherry-Pick

Definition: Applies changes from a selected commit to the current branch.

```
git switch main
git cherry-pick <commit-hash>
```

### Comparison

| Merge               | Rebase                | Cherry-Pick             |
| ------------------- | --------------------- | ----------------------- |
| Integrates branches | Replays commits       | Applies selected commit |
| Preserves ancestry  | Rewrites commits      | Creates new commit      |
| Team collaboration  | Local history cleanup | Specific fixes          |

Remember: Avoid rebasing shared published commits without coordinating with collaborators.

## 6. Git Conflict Resolution

Definition: A merge conflict occurs when Git cannot automatically combine changes.

### Practical

```
# Create feature branch
git switch -c feature-test
echo "Feature Change" > index.html
git add .
git commit -m "Feature update"

# Modify same file on main
git switch main
echo "Main Change" > index.html
git add .
git commit -m "Main update"

# Merge branches
git merge feature-test
```

### Resolve Conflict

```
# Edit file with desired content
echo "Resolved Content" > index.html

# Complete merge
git add index.html
git commit -m "Resolved conflict"

# Verify
git status
```

To cancel an in-progress conflicted merge:

```
git merge --abort
```

## 7. Git Stashing

Definition: Temporarily saves uncommitted changes without creating a regular commit.

```
# Modify tracked file
echo "Temporary Work" >> index.html

# Save changes
git stash

# List stashes
git stash list

# Restore while keeping stash entry
git stash apply

# Remove applied working changes before next demo
git restore index.html

# Restore and remove stash
git stash pop
```

Remember: `apply` retains the stash entry; `pop` removes it after successful application. By default, untracked files are not stashed; use `git stash -u` to include them.

## 8. Git Rollback Techniques

### Git Reset

Definition: Moves HEAD to another commit and optionally changes staging and working files.

```
# Undo commit, keep changes staged
git reset --soft HEAD~1

# Undo commit, keep changes unstaged
git reset --mixed HEAD~1

# Discard tracked changes
git reset --hard HEAD~1
```

### Git Revert

Definition: Creates a new commit that reverses changes from an earlier commit.

```
git revert HEAD
```

### Git Restore

Definition: Restores working files or unstages changes.

```
# Discard unstaged changes
git restore index.html

# Unstage file
git restore --staged index.html
```

### Reset vs Revert vs Restore

| Command         | Use Case                            |
| --------------- | ----------------------------------- |
| `reset --soft`  | Undo commit, retain staged changes  |
| `reset --mixed` | Undo commit, retain working changes |
| `reset --hard`  | Discard tracked local changes       |
| `revert`        | Safely undo committed changes       |
| `restore`       | Restore files or unstage            |

Important: Practice `git reset --hard` only in a disposable repository. Prefer `git revert` for commits already shared with others.

## 9. Git Best Practices

- Write meaningful commit messages.
- Commit small, logical changes.
- Use feature branches for development.
- Maintain a `.gitignore` file.
- Never commit credentials, passwords, or secrets.
- Review code using GitHub pull requests.
- Avoid force-pushing shared branches.
- Prefer revert for undoing shared commits.

## 10. Training Assignments

| No. | Assignment                       | Expected Outcome            |
| --- | -------------------------------- | --------------------------- |
| 1   | Install and configure Git        | Git setup                   |
| 2   | Create repository with 5 commits | Commit history              |
| 3   | Connect and push to GitHub       | Remote repository           |
| 4   | Clone, pull and push             | Code synchronization        |
| 5   | Create and merge branches        | Branch integration          |
| 6   | Practice rebase and cherry-pick  | History management          |
| 7   | Generate and resolve conflict    | Conflict resolution         |
| 8   | Practice stash and pop           | Temporary change management |
| 9   | Practice reset, revert, restore  | Rollback operations         |

## 11. Final Practical Assignment

Project: `git-devops-practice`

Objective: Demonstrate Git version control and GitHub collaboration.

Tasks:

1. Create a local Git repository and connect it to GitHub.
2. Add `index.html`, `app.py`, and `README.md`.
3. Create at least five commits.
4. Create `feature-login` and `feature-dashboard` branches.
5. Merge both branches into `main`.
6. Generate and resolve one merge conflict.
7. Demonstrate rebase and cherry-pick.
8. Practice Git stash.
9. Demonstrate reset, revert, and restore.
10. Push final changes to GitHub.

Deliverable: GitHub repository URL, commit history, branch history, and completed practical exercises.

Training Outcome: Learners will be able to manage Git repositories, collaborate through GitHub, work with branches, resolve conflicts, and safely manage changes and rollbacks.
