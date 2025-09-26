# Update Local Command - Project-Specific Command Modifier

## Purpose
Updates existing local Claude Code commands in the current project's `.claude/commands/` directory with new instructions, focusing solely on project-specific customizations without affecting workspace documentation.

## Generated From
**Meta-command input:** `create a similar one but that only updates a local command (not anything in the workspace)`

## Command Usage

```bash
/update-local-command {command-name} {update instructions}
```

## How It Works

### 1. Local-Only Focus
- **Target:** `.claude/commands/{name}.md` in current project
- **No Workspace Sync:** Ignores `~/.claude/workspace/` entirely
- **Project Context:** Uses actual project files and structure
- **Rapid Iteration:** Fast updates without synchronization overhead

### 2. Project-Aware Processing
- Detects current project structure and technologies
- References actual files and directories in examples
- Uses project-specific naming conventions and patterns
- Integrates with existing project toolchain

### 3. Local Customization Benefits
- Perfect for project-specific command modifications
- Enables experimentation without affecting global commands
- Allows team-specific workflow integration
- Supports technology-specific adaptations

## Real-World Examples

### TypeScript Project Customization
```bash
/update-local-command ensure-local-principle add TypeScript interface validation and tsconfig.json compliance checks
```

**Result:** Enhanced principle detection that validates TypeScript configurations and interface definitions specific to your project.

### React Project Integration
```bash
/update-local-command session-summary include component count, hook usage status, and React DevTools integration
```

**Result:** Session summaries now include React-specific metrics and development tool status.

### Docker Development Enhancement
```bash
/update-local-command commit-smart include Docker container status and image build validation in commit checks
```

**Result:** Commit process now validates Docker setup and container health before allowing commits.

### Monorepo Workspace Adaptation
```bash
/update-local-command add-context7-mandate detect current workspace package and customize documentation requirements accordingly
```

**Result:** Context7 mandate adapts based on which package in the monorepo is being worked on.

## Use Cases by Project Type

### Frontend Projects
```bash
# React/Vue projects
/update-local-command session-summary add build status, bundle size, and lighthouse scores

# Next.js projects
/update-local-command commit-smart validate page routes and API endpoints before commit
```

### Backend Projects
```bash
# API projects
/update-local-command ensure-local-principle add API documentation standards and endpoint validation

# Database projects
/update-local-command session-summary include migration status and connection health
```

### Full-Stack Projects
```bash
# Include both frontend and backend status
/update-local-command session-summary combine client build status with server health and database migrations
```

### DevOps Projects
```bash
# Infrastructure projects
/update-local-command commit-smart validate Terraform plans and Kubernetes manifests

# CI/CD projects
/update-local-command session-summary include pipeline status and deployment health
```

## Local vs Global Strategy

### When to Use Local Updates

**Project-Specific Needs:**
- Commands need to reference specific project files
- Integration with project-specific tools
- Team workflow customizations
- Technology stack adaptations

**Rapid Experimentation:**
- Testing command modifications quickly
- Trying new approaches safely
- Iterating on command improvements
- Validating ideas before global adoption

**Temporary Modifications:**
- Short-term project requirements
- Sprint-specific command adjustments
- Prototype feature support
- Emergency workflow adaptations

### Integration Workflow

```bash
# 1. Copy global command locally (if needed)
cp ~/.claude/commands/session-summary.md ./.claude/commands/

# 2. Customize for project
/update-local-command session-summary add project-specific status checks

# 3. Test and refine
# [use command repeatedly, making adjustments]

# 4. Extract successful patterns globally (optional)
/update-global-command session-summary incorporate successful local patterns from project X
```

## Project Context Examples

### Before: Generic Global Command
```markdown
## Implementation
1. Check git status
2. List recent commits
3. Show current branch
```

### After: Project-Customized Local Command
```markdown
## Implementation
1. Check git status in current React monorepo
2. List recent commits with Jira ticket references
3. Show current feature branch and associated PR
4. Include component test coverage for affected files
5. Display Docker container status for local development
6. Check if Storybook stories exist for new components
```

## Advanced Features

### Technology Detection
- Automatically detects project type (React, Vue, Node.js, Python, etc.)
- Identifies build tools (Webpack, Vite, Rollup, etc.)
- Recognizes testing frameworks (Jest, Cypress, Playwright, etc.)
- Adapts commands based on detected stack

### File System Integration
- References actual project structure in examples
- Uses real file paths and directory names
- Integrates with existing project scripts and tools
- Validates against current project configuration

### Team Workflow Adaptation
- Adapts to team naming conventions
- Integrates with team tools (Jira, Slack, etc.)
- Follows team-specific processes
- Uses team coding standards and practices

## Error Handling

### Missing Local Commands Directory
```
❌ No .claude/commands/ directory found
💡 Suggestion: Create local commands directory first
🔧 Quick fix: mkdir -p .claude/commands
```

### Command Not Found Locally
```
❌ Local command 'session-summary' not found
📋 Available local commands: [list]
💡 Copy from global: cp ~/.claude/commands/session-summary.md ./.claude/commands/
```

### Project Context Issues
```
❌ Cannot detect project type
💡 Suggestion: Ensure you're in project root directory
🔧 Check for: package.json, requirements.txt, Cargo.toml, etc.
```

## Maintenance and Evolution

### Regular Updates
- Update local commands as project evolves
- Adapt to new technologies added to project
- Refine based on team feedback
- Remove obsolete project-specific features

### Team Synchronization
- Share successful local modifications with team
- Document project-specific command usage
- Create team standards for local customizations
- Maintain consistency across team members

### Global Pattern Extraction
- Identify local patterns worth globalizing
- Extract successful approaches to global commands
- Maintain separation between project-specific and universal features
- Contribute improvements back to global command library

---

*This command enables rapid, project-focused command customization without the overhead of workspace synchronization, perfect for tailoring your development workflow to specific project needs.*