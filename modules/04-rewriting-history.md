# Module 04 — Rewriting History

## Objectives
- Amend and fixup commits
- Reset vs revert vs rebase
- Recover with reflog

## Concepts
- Reset moves branch refs; revert creates new inverse commits
- Rebase rewrites commits; interactive rebase edits/combines/reorders
- Reflog tracks ref movements locally

## Key commands
- git commit --amend, commit --fixup/--squash
- git reset --soft|--mixed|--hard, git revert
- git rebase [-i], git reflog, git cherry-pick

## Examples
```bash
# Amend last commit message
git commit --amend -m "feat: refine message"

# Fixup a prior commit
git commit --fixup=<commit>
GIT_SEQUENCE_EDITOR=true git rebase -i --autosquash <base>

# Reset types
git reset --soft HEAD~1   # keep index+worktree
git reset --mixed HEAD~1  # keep worktree, unstage
git reset --hard HEAD~1   # discard local changes

# Revert a bad commit on shared branch
git revert <commit-sha>

# Interactive rebase to squash and reorder
git rebase -i HEAD~5

# Recover with reflog
git reflog
# Find prior HEAD and reset back
git reset --hard HEAD@{2}
```

## Try it
- Make three small commits, then squash them into one via interactive rebase
- Create a bad change on main and revert it
- Use reflog to recover a branch after a mistaken reset

## Pitfalls
- Never rebase or reset published/shared branches unless everyone agrees
- Always create a safety branch before aggressive history edits

## References
- `git help reset`, `git help rebase`, `git help reflog`
