# New Project Setup Workflow

A comprehensive workflow for setting up Claude Code in new projects.

## 🚀 Quick Setup Checklist

### 1. Initialize Claude Configuration
```bash
# Copy base template
cp ~/.claude/workspace/templates/CLAUDE.md ./CLAUDE.md

# Create .claude directory (if using commands)
mkdir -p .claude/commands

# Set up local git ignore for Claude files
echo "CLAUDE.md" >> .git/info/exclude
echo ".claude/" >> .git/info/exclude
```

### 2. Customize CLAUDE.md for Project

- [ ] Replace `[PROJECT DESCRIPTION]` with actual project details
- [ ] Update `[FRAMEWORK]` sections with relevant technology
- [ ] Add project-specific validation commands
- [ ] Configure framework-specific best practices
- [ ] Set up proper file organization patterns

### 3. Add Relevant Commands

Choose commands based on project type:

```bash
# For Git-heavy projects
cp -r ~/.claude/workspace/commands/git .claude/commands/

# For development-focused projects
cp -r ~/.claude/workspace/commands/development .claude/commands/

# For analysis-heavy projects
cp -r ~/.claude/workspace/commands/analysis .claude/commands/
```

### 4. Project-Specific Adaptations

#### Frontend Projects (React/Vue/Angular)
```bash
# Add frontend-specific patterns
cp ~/.claude/workspace/templates/project-setups/frontend-patterns.md ./

# Update CLAUDE.md with:
# - Component organization patterns
# - State management conventions
# - Build/dev server commands
# - Testing frameworks
```

#### Backend Projects (Node/Python/Go)
```bash
# Add backend-specific patterns
cp ~/.claude/workspace/templates/project-setups/backend-patterns.md ./

# Update CLAUDE.md with:
# - API design patterns
# - Database interaction patterns
# - Error handling conventions
# - Logging/monitoring setup
```

#### Full-Stack Projects
```bash
# Add both frontend and backend patterns
# Consider separate CLAUDE.md files for different parts
# Or comprehensive single file with clear sections
```

### 5. Validation Commands

Add project-specific validation to CLAUDE.md:

```bash
# JavaScript/TypeScript projects
pnpm lint && pnpm type-check

# Python projects
python -m mypy . && python -m pytest

# Go projects
go vet ./... && go test ./...

# Rust projects
cargo check && cargo test
```

### 6. Test the Setup

```bash
# Verify git ignore is working
git status  # Should be clean

# Verify CLAUDE.md is accessible
ls -la CLAUDE.md

# Test validation commands work
[run your validation commands]
```

## 🔄 Ongoing Maintenance

### Document New Discoveries
When you find useful patterns in this project:

```bash
# Add to workspace for future reuse
cp ./useful-pattern.md ~/.claude/workspace/knowledge-base/best-practices/

# Update templates if pattern is widely applicable
```

### Keep Templates Current
```bash
# Periodically update your workspace
cd ~/.claude/workspace
git add .
git commit -m "Add patterns from project X"
```

## 📋 Project Type Quick Starts

### Vue + TypeScript + Pinia
```bash
cp ~/.claude/workspace/templates/project-setups/vue-typescript.md ./project-setup.md
# Update CLAUDE.md with Vue-specific patterns
# Add Element Plus patterns if using
# Configure Pinia store conventions
```

### React + TypeScript + Redux
```bash
cp ~/.claude/workspace/templates/project-setups/react-typescript.md ./project-setup.md
# Update CLAUDE.md with React patterns
# Add Redux/RTK patterns
# Configure component organization
```

### Node.js + Express + PostgreSQL
```bash
cp ~/.claude/workspace/templates/project-setups/node-express.md ./project-setup.md
# Update CLAUDE.md with backend patterns
# Add database interaction patterns
# Configure error handling middleware
```

---

*This workflow ensures consistent Claude Code setup while allowing project-specific customization.*