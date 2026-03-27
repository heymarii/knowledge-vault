# Git — The Things I Actually Use

*Not a comprehensive tutorial. Just the commands I reach for regularly.*

## Daily Workflow

```bash
git status                          # What's changed?
git add -p                          # Stage changes interactively (review each chunk)
git commit -m "feat: add X"         # Commit with conventional commit format
git push                            # Push to remote
```

## Branch Workflow

```bash
git checkout -b feature/my-feature  # Create + switch to new branch
git checkout main                   # Switch to main
git merge feature/my-feature        # Merge branch into current
git branch -d feature/my-feature    # Delete merged branch
```

## Undoing Things

```bash
git restore filename.py             # Discard unstaged changes to a file
git restore --staged filename.py    # Unstage a file (keep changes)
git reset HEAD~1                    # Undo last commit (keep changes staged)
git reset --hard HEAD~1             # Undo last commit AND discard changes ⚠️
```

## Useful One-Liners

```bash
git log --oneline -10               # Last 10 commits, compact view
git diff HEAD~1                     # What changed in last commit
git stash                           # Temporarily stash changes
git stash pop                       # Restore stashed changes
git cherry-pick abc123              # Apply a specific commit to current branch
```

## Conventional Commits

I use this format for commit messages:

```
type(scope): description

feat:     New feature
fix:      Bug fix
docs:     Documentation only
style:    Formatting, no logic change
refactor: Code restructure, no behavior change
test:     Adding/fixing tests
chore:    Build process, dependencies
```

---

*For everything else: `git help <command>` or [git-scm.com](https://git-scm.com/docs)*
