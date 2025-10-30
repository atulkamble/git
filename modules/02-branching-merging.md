# Module 02 — Branching & Merging

## Objectives
- Create and switch branches
- Merge fast-forward and non-fast-forward
- Resolve conflicts and use stash/worktrees

## Concepts
- Branch = movable pointer to a commit
- Merge strategies: fast-forward vs merge commit
- Conflict resolution and the index (3-way merge)

## Key commands
- git branch, switch/checkout, merge, rebase (preview), stash, worktree

## Examples
```bash
# Create a branch and work on it
git switch -c feature/login
echo "login" > login.txt
git add login.txt && git commit -m "feat: add login"

# Switch back and merge
git switch main
git merge feature/login --no-ff -m "merge: feature/login"

# Conflict demo
git switch -c tweak-readme
sed -i '' '1s/^/Top line\n/' README.md || true
git commit -am "tweak: top line"

git switch main
sed -i '' '1s/^/Different top\n/' README.md || true
git commit -am "tweak: different top"

git merge tweak-readme
# Edit conflict markers <<<<<<, ======, >>>>>>> then stage
git add README.md
git commit

# Stash quick changes
echo "temp" >> scratch.txt
git stash push -m "wip: scratch"
# Bring them back later
git stash list
git stash apply stash@{0}

# Worktrees: multiple branches checked out simultaneously
mkdir -p ../wt && git worktree add ../wt/bugfix bugfix/typo
```

## Try it
- Create two branches that both edit the same line; trigger and resolve a conflict
- Use `git log --oneline --graph --decorate` to visualize merges
- Use a worktree to fix a bug while keeping your feature branch open

## Pitfalls
- Long-lived branches drift; rebase/merge main frequently
- Stashes can pile up; name them and clean regularly

## References
- Pro Git chapters on branching and merging
- `git help merge`, `git help worktree`
