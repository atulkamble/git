# Syllabus

Estimated total time: 14–20 hours (self-paced, modular)

## Modules
1. Basics of Git (`modules/01-basics.md`)
   - Installing/configuring Git, repository lifecycle, staging, committing, inspecting history, ignoring files
2. Branching and Merging (`modules/02-branching-merging.md`)
   - Branch creation, switching, merging, conflict resolution, stash, worktrees basics
3. Remotes and GitHub (`modules/03-remote-github.md`)
   - Clone, remotes (origin/upstream), fetch, pull, push, auth (SSH/HTTPS), PR overview
4. Rewriting History (`modules/04-rewriting-history.md`)
   - Amend, reset (soft/mixed/hard), revert, rebase (incl. interactive), cherry-pick, reflog recovery
5. Collaboration & Workflows (`modules/05-collaboration-workflows.md`)
   - Branching models (GitFlow, trunk), code reviews, protected branches, commit messages, semantic versioning
6. Advanced Essentials (`modules/06-advanced.md`)
   - Bisect, blame/grep, stash-apply/pop/branch, worktrees, maintenance overview
7. Git Internals: Objects & Refs (`modules/07-internals-objects-refs.md`)
   - Blobs, trees, commits, tags; refs/HEAD; object IDs; packfiles; plumbing vs porcelain
8. Performance & Maintenance (`modules/08-performance-and-maintenance.md`)
   - gc/maintenance, commit-graph, bitmaps, partial clone, shallow clone, large history strategies
9. Monorepos & Sparse Checkout (`modules/09-monorepos-sparse-checkout.md`)
   - Sparse checkout, cone mode, partial clone, worktrees for monorepo workflows
10. Submodules vs Subtrees (`modules/10-submodules-subtrees.md`)
    - Trade-offs, commands, common pitfalls, alternatives (vendoring, packages)
11. Security & Signing (`modules/11-security-signing-policies.md`)
    - GPG/S/MIME signing, Sigstore/cosign/GitHub Vigilant, branch protection, CODEOWNERS, verified status
12. GitHub Actions: CI/CD Advanced (`modules/12-github-actions-advanced.md`)
    - Caching, matrix builds, required checks, environments, secrets, reusable workflows
13. GitHub Automation & DevEx (`modules/13-gh-cli-codespaces-automation.md`)
    - GitHub CLI (gh), Codespaces, issue templates, PR templates, Dependabot, bots
14. Git LFS & Large Repos (`modules/14-lfs-and-large-repos.md`)
    - LFS storage, migration, pointers, bandwidth; alternatives and trade-offs
15. Hooks, Attributes & Custom Merges (`modules/15-hooks-attributes-merge-drivers.md`)
    - pre-commit/pre-push, lint staged, .gitattributes, merge drivers, text vs binary
16. Debugging with Bisect & History Analysis (`modules/16-bisect-and-debugging.md`)
    - bisect scripts, blame, range-diff, pickaxe, log formats, profiling changes

## Labs
- Lab 01: Local Repo Fundamentals (`labs/lab01-local-repo.md`) – 45–60 min
- Lab 02: Branching & Conflicts (`labs/lab02-branching.md`) – 45–60 min
- Lab 03: GitHub PR Workflow (`labs/lab03-github-fork-pr.md`) – 60–90 min
- Lab 04: Rebase & History Surgery (`labs/lab04-rebase-merge-conflicts.md`) – 45–60 min
- Lab 05: CI with GitHub Actions (`labs/lab05-ci-with-actions.md`) – 45–60 min
- Lab 06: Monorepo & Sparse Checkout (`labs/lab06-sparse-monorepo.md`) – 45–60 min
- Lab 07: Security & Signing (`labs/lab07-signing-and-protection.md`) – 45–60 min

## Cheatsheets
- Git Cheatsheet (`cheatsheets/git-cheatsheet.md`)
- GitHub Cheatsheet (`cheatsheets/github-cheatsheet.md`)
- Rebase/Reset Decision Guide (`cheatsheets/rewrite-decision-guide.md`)

## Learning outcomes
By the end, you will be able to:
- Track and navigate project history confidently
- Branch, merge, and resolve conflicts with minimal stress
- Collaborate using GitHub PRs and reviews
- Rewrite history safely and recover from mistakes
- Optimize performance for large/monorepo setups
- Secure your supply chain with signing and protected workflows
- Build robust CI/CD with GitHub Actions and automation
