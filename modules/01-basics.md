# Module 01 — Git Basics

## Objectives
- Configure Git identity and defaults
- Initialize repositories, stage and commit changes
- Inspect status and history, restore files

## Concepts
- Repository: working tree + index (staging area) + .git database
- Snapshot model: commits point to trees/blobs; branches name commit IDs
- Three states: modified, staged, committed

## Setup
- Install Git 2.30+
- Configure identity and editor

## Key commands
- git config, git init/clone, status, add, commit, log, show, diff, restore, rm, mv, ignore

## Examples
```bash
# One-time identity
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
# Useful defaults
git config --global init.defaultBranch main
git config --global pull.rebase false

# New repo
mkdir hello-git && cd hello-git
echo "Hello" > readme.txt
git init
git status

git add readme.txt
git commit -m "feat: add readme"

git log --oneline --graph --decorate

echo "More" >> readme.txt
# See changes
git diff
# Stage and commit
git add -p
git commit -m "chore: update readme"

# Restore a file from last commit
git restore --source=HEAD -- readme.txt
```

## Try it
- Create a repo, add two files, make three commits with meaningful messages
- Use `git show` to view a specific commit and `git diff HEAD~1..HEAD`

## Pitfalls
- Committing secrets; add patterns to `.gitignore`
- Large binaries bloat history; consider Git LFS later

## References
- Pro Git book chapters 1–2
- `git help <command>` for built-in docs
