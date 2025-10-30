# Module 03 — Remotes & GitHub

## Objectives
- Work with remote repositories
- Authenticate via HTTPS or SSH
- Use GitHub for forks, PRs, and reviews

## Concepts
- Remote names (origin, upstream), tracking branches
- Fetch vs pull vs push
- GitHub PR lifecycle and reviews

## Key commands
- git clone, remote, fetch, pull, push, remote set-url
- GitHub: PRs, issues, reviews, branch protection (UI)
- gh CLI (optional): `gh auth`, `gh repo`, `gh pr`

## Examples
```bash
# Clone and inspect remotes
git clone https://github.com/owner/repo.git
cd repo
git remote -v

# Add upstream for fork workflows
git remote add upstream https://github.com/original/repo.git

git fetch --all --prune
# Update local main from upstream
git switch main
git pull --ff-only upstream main

# Push a feature branch
git switch -c feature/awesome
# ... commits ...
git push -u origin feature/awesome

# Create a PR (using GH CLI)
# gh auth login
# gh pr create --fill --base main --head feature/awesome
```

## Try it
- Create a fork, add `upstream`, fetch and sync with upstream main
- Push a branch to your fork and open a PR
- Ask a teammate to review and suggest changes

## Pitfalls
- Force-pushing shared branches is dangerous; protect `main`
- Keep local main updated from upstream to reduce conflicts

## References
- GitHub Docs: About forks and PRs
- `git help remote`, `gh help`
