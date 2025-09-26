# Add Command Global - Meta-Command Generator

## Purpose
A meta-command that creates new Claude Code commands based on natural language input. This allows you to rapidly expand your command library by simply describing what you want in plain English.

## Usage

```bash
/add-command-global {natural language description of what you want}
```

### Examples

**Example 1: Add principles to CLAUDE.md**
```bash
/add-command-global update local claude md with incremental development principles, simple approach, less is more, and clean code practices
```

**Example 2: Create git workflow command**
```bash
/add-command-global create command to commit all changes with semantic commit message and push to origin
```

**Example 3: Add documentation standards**
```bash
/add-command-global append to project readme with api documentation standards and examples
```

## How It Works

### 1. Natural Language Parsing
The command intelligently parses your input to identify:
- **Action**: What you want to do (update, create, append, add, etc.)
- **Target**: What file or system to modify (CLAUDE.md, README, package.json, etc.)
- **Content**: What principles, rules, or content to include

### 2. Smart Command Generation
Based on your input, it:
- Generates an appropriate command name (e.g., `update-incremental-principles.md`)
- Creates complete AI instructions for Claude to follow
- Includes implementation steps, usage examples, and benefits
- Handles edge cases and error scenarios

### 3. Dual File Creation
Creates both:
- **Executable Command**: `~/.claude/commands/{name}.md` - AI instructions
- **Documentation**: `~/.claude/workspace/commands/{category}/{name}.md` - User docs

## Generated Command Categories

The system automatically categorizes commands into workspace directories:

- **development/** - Development workflow and coding practices
- **git/** - Git operations and version control
- **analysis/** - Code analysis and review commands
- **deployment/** - Deployment and CI/CD related commands
- **setup/** - Project initialization and configuration
- **documentation/** - Documentation and README management

## Command Patterns Supported

### File Update Commands
```bash
/add-command-global update {file} with {content/principles}
```
Creates commands that append content to existing files.

### Creation Commands
```bash
/add-command-global create {what} for {purpose}
```
Creates commands that generate new files or structures.

### Analysis Commands
```bash
/add-command-global analyze {target} for {criteria}
```
Creates commands that examine code or files.

### Workflow Commands
```bash
/add-command-global automate {process} with {steps}
```
Creates commands that handle multi-step processes.

## Success Output

When successful, you'll see:

```
✅ Command Created Successfully!

Command Name: /your-new-command
File Location: ~/.claude/commands/your-new-command.md
Documentation: ~/.claude/workspace/commands/category/your-new-command.md

What it does: Brief description of functionality

Try it now: Type /your-new-command to use your new command!
```

## Best Practices

### Writing Good Descriptions
- **Be specific**: Instead of "make it better", say "add clean code principles"
- **Include context**: Specify the target file or system
- **Mention methodology**: Include the approach or philosophy you want

### Good Examples
✅ `update CLAUDE.md with TDD practices and testing requirements`
✅ `create git workflow command for feature branch development`
✅ `add typescript configuration standards to project setup`

### Poor Examples
❌ `make things better` (too vague)
❌ `fix stuff` (no clear target or action)
❌ `do something with code` (no specific intent)

## Integration with Existing Workflow

This meta-command fits into the workspace evolution strategy:

1. **Discover needs** during regular development
2. **Create commands** using natural language with `/add-command-global`
3. **Use and refine** the generated commands
4. **Share patterns** via workspace documentation
5. **Evolve methodology** based on what works

## Advanced Usage

### Chaining Commands
Create commands that work together:
```bash
/add-command-global create project initialization command that sets up CLAUDE.md, gitignore, and development standards
```

### Conditional Logic
Include conditional behavior:
```bash
/add-command-global update package.json scripts but only if typescript is detected in project
```

### Multi-file Operations
Handle multiple files:
```bash
/add-command-global create documentation sync command that updates both README and CLAUDE.md with project changes
```

## Troubleshooting

### Command Not Working as Expected
1. Check the generated command file in `~/.claude/commands/`
2. Review the AI instructions for clarity
3. Test with simpler inputs first
4. Regenerate with more specific language

### Naming Conflicts
If a command name already exists, the system will:
- Warn about the conflict
- Suggest alternative names
- Ask for confirmation before overwriting

### Unclear Input
If your description is ambiguous, Claude will:
- Ask for clarification about the specific action
- Request more details about the target
- Suggest alternative approaches

## Evolution and Maintenance

### Regular Cleanup
- Review generated commands monthly
- Archive or remove unused commands
- Refactor successful patterns into templates

### Pattern Recognition
- Document successful command patterns
- Create templates for common use cases
- Share effective descriptions with team

### Workspace Integration
- Commands are automatically documented in workspace
- Use workspace version control to track command evolution
- Cherry-pick successful commands to other projects

---

*This meta-command transforms natural language into actionable Claude Code commands, making your development workflow continuously adaptable and self-improving.*