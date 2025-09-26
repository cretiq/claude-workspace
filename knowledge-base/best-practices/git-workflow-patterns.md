# Git Workflow Patterns for Claude Code

Best practices for Git workflows when working with Claude Code.

## 🚨 Branch Management

### Before Starting Work
```bash
# Always sync with latest master/main
git fetch origin
git checkout master
git pull origin master

# Create feature branch
git checkout -b feature/descriptive-name
```

### Avoiding Duplicate Work
**Problem**: Your local branch has commits that are already merged via PR.

**Prevention**:
```bash
# After PR is merged, always:
1. Switch to master: git checkout master
2. Pull latest: git pull origin master
3. Delete feature branch: git branch -D feature/old-branch
4. Start fresh: git checkout -b feature/new-work
```

**Recovery** (if you're already in duplicate state):
```bash
# Check branch status
git status
git log --oneline -5
git log --oneline origin/master -5

# If your commits duplicate merged work:
git fetch origin
git reset --hard origin/master
```

## 🔍 Investigating Diverged Branches

### Diagnostic Commands
```bash
# Check branch relationship
git status

# View recent local commits
git log --oneline -10

# View recent origin commits
git log --oneline origin/master -10

# Compare with graph view
git log --oneline --graph --all -10

# Check reflog for recent operations
git reflog --oneline -10
```

### Understanding Git Status Messages
```bash
# "Your branch and 'origin/master' have diverged, and have 1 and 16 different commits"
# Means: You have 1 local commit, origin has 16 commits you don't have

# "Your branch is ahead of 'origin/master' by 1 commit"
# Means: You have 1 commit that origin doesn't have (safe to push)

# "Your branch is behind 'origin/master' by 5 commits"
# Means: Origin has 5 commits you don't have (need to pull)
```

## 🛠️ Common Recovery Patterns

### Reset to Origin (Lose Local Changes)
```bash
git fetch origin
git reset --hard origin/master
# WARNING: This permanently deletes your local commits
```

### Merge Approach (Keep Local Changes)
```bash
git pull origin master
# Creates merge commit, keeps your local work
# Use when your local changes are truly new work
```

### Rebase Approach (Clean History)
```bash
git fetch origin
git rebase origin/master
# Replays your commits on top of latest master
# Use for small feature branches
```

## 🎯 PR Workflow Best Practices

### Before Creating PR
```bash
# Ensure branch is clean
git status

# Sync with latest master
git checkout master
git pull origin master
git checkout feature/your-branch
git rebase master  # or git merge master

# Push to origin
git push -u origin feature/your-branch
```

### After PR is Merged
```bash
# Switch to master
git checkout master

# Pull merged changes
git pull origin master

# Delete local feature branch
git branch -D feature/merged-branch

# Clean up remote tracking
git remote prune origin
```

## 🚫 Anti-Patterns to Avoid

### ❌ Working Directly on Master
```bash
# DON'T do this:
git checkout master
# make changes
git commit -m "changes on master"

# DO this instead:
git checkout -b feature/my-changes
# make changes
git commit -m "changes on feature branch"
```

### ❌ Not Syncing Before Starting
```bash
# DON'T start work on stale master:
git checkout master
git checkout -b feature/new-work  # without pulling latest

# DO sync first:
git checkout master
git pull origin master
git checkout -b feature/new-work
```

### ❌ Committing After PR is Merged
```bash
# DON'T commit work that's already merged:
# (Check if your work is already in master via PR first)

# DO check master first:
git checkout master
git pull origin master
# Check if your changes are already there
```

## 🔧 Useful Git Aliases

```bash
# Add to ~/.gitconfig
[alias]
    sync = "!git checkout master && git pull origin master"
    new-branch = "!f() { git sync && git checkout -b $1; }; f"
    cleanup = "!git checkout master && git pull origin master && git branch --merged | grep -v master | xargs -n 1 git branch -d"
    diverged = "!git log --oneline --graph --decorate --all -10"

# Usage:
git sync                    # Sync with master
git new-branch feature/foo  # Create new branch from latest master
git cleanup                 # Delete merged branches
git diverged               # Visualize branch relationships
```

## 📋 Daily Workflow Checklist

### Starting Work
- [ ] `git sync` (sync with master)
- [ ] `git checkout -b feature/descriptive-name`
- [ ] Begin development

### During Development
- [ ] Commit regularly with descriptive messages
- [ ] Push branch periodically: `git push -u origin feature/branch-name`

### Before Creating PR
- [ ] `git sync` and `git rebase master` (or merge)
- [ ] Resolve any conflicts
- [ ] Push final changes
- [ ] Create PR

### After PR Merged
- [ ] `git sync` (get merged changes)
- [ ] `git branch -D feature/merged-branch` (clean up)
- [ ] Start next feature from latest master

---

*Following these patterns prevents the confusion of duplicate commits and keeps your git history clean.*