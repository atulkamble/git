# Module 06 — Advanced Essentials

## Objectives
- Use advanced inspection and debugging tools
- Manage parallel work with worktrees
- Maintain repository health

## Topics
- grep/blame/log formats, range-diff
- stash apply/pop/branch; worktrees
- maintenance, gc, fsmonitor

## Commands
```bash
# Inspect history deeply
git log --oneline --graph --decorate --stat
git log -S 'functionName' -- path/to/file

git blame -L 10,40 path/to/file

git range-diff main...feature

# Worktrees
git worktree add ../wt/feature feature

# Maintenance (modern)
git maintenance run --task=commit-graph --task=gc --task=prefetch
```

## Try it
- Use pickaxe `-S` to find where a function appeared/changed
- Create two worktrees: one for a hotfix, one for a feature
- Run `git maintenance` and inspect performance

## Pitfalls
- `git gc --prune=now` can remove unreachable objects; ensure no ongoing rebases

## References
- `git help range-diff`, `git help maintenance`, `git help worktree`
