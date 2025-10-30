# Module 05 — Collaboration & Workflows

## Objectives
- Choose an effective branching model
- Standardize reviews, PR templates, and commit messages
- Use protected branches and required checks

## Concepts
- Trunk-based vs GitFlow vs feature branches
- Small PRs, fast feedback, clear ownership
- Semantic commit messages and conventional releases

## Key practices
- CODEOWNERS for review routing
- Protected branches with required status checks
- PR and issue templates

## Examples
```bash
# CODEOWNERS example (.github/CODEOWNERS)
# Frontend files owned by web team
frontend/**  @org/web-team

# PR template (.github/pull_request_template.md)
- Summary
- Type: feat | fix | chore | docs | refactor
- Tests: added/updated
- Screenshots/Notes

# Commit message convention
feat(ui): add dark mode toggle
fix(api): handle 404 in user lookup
```

## Try it
- Add CODEOWNERS and a PR template to a repo
- Configure branch protection on main with required checks
- Adopt semantic commits and add a commit lint in CI

## Pitfalls
- Overly rigid branching can slow teams; prefer simpler models
- Large PRs are hard to review; aim for <300 lines changed

## References
- GitHub Docs: Branch protection rules, CODEOWNERS
- Conventional Commits
