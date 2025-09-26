# Git Local Ignore Pattern

## Problem
Need to ignore files locally without affecting the shared `.gitignore` file or other developers.

## Solution
Use `.git/info/exclude` for local-only file exclusions.

## Command
```bash
# Add files/patterns to local exclude
echo "filename.txt" >> .git/info/exclude
echo "directory/" >> .git/info/exclude
echo "*.local" >> .git/info/exclude
```

## Usage Examples

### Ignore Claude Code files locally
```bash
echo "CLAUDE.md" >> .git/info/exclude
echo ".claude/" >> .git/info/exclude
```

### Ignore development files
```bash
echo ".vscode/settings.json" >> .git/info/exclude
echo "*.log" >> .git/info/exclude
echo "tmp/" >> .git/info/exclude
```

## Verification
```bash
# Check if file is being ignored
git check-ignore filename.txt

# Check with verbose output to see source
git check-ignore -v filename.txt

# Verify git status is clean
git status
```

## Benefits
- ✅ **Local-only** - doesn't affect other developers
- ✅ **No repository changes** - doesn't modify .gitignore
- ✅ **Persistent** - survives git operations
- ✅ **Clean** - files completely invisible to git

## When to Use
- Personal development files (IDE settings)
- Local debugging files
- Temporary files specific to your workflow
- Files that shouldn't be shared but need to exist locally

## Official Documentation
From Git docs: "Patterns which are specific to a particular repository but which do not need to be shared with other related repositories should go into the `$GIT_DIR/info/exclude` file."