# Update Global Command - Command Modifier

## Purpose
Updates existing Claude Code commands with new instructions while automatically synchronizing both the executable command file and its workspace documentation. Ensures complete consistency between command logic and user-facing documentation.

## Generated From
**Meta-command input:** `a command that updates an existing global command with the instructions following the command. this command also takes into consideration the command(docs) in .claude/workspace, analyze it thoroughly and update it, too, accordingly.`

## Command Usage

```bash
/update-global-command {command-name} {update instructions}
```

## How It Works

### 1. Dual-File System Management
- **Main Command File:** `~/.claude/commands/{name}.md` - AI execution instructions
- **Workspace Documentation:** `~/.claude/workspace/commands/{category}/{name}.md` - User documentation
- **Synchronized Updates:** Both files are updated consistently with new functionality

### 2. Intelligent Update Processing
The command analyzes your instructions to determine:
- **Additive Changes:** New functionality to append
- **Replacement Changes:** Existing content to modify
- **Enhancement Changes:** Expanding existing capabilities
- **Structural Changes:** Organization improvements

### 3. Smart Content Integration
- Preserves existing working functionality
- Seamlessly integrates new instructions
- Maintains consistent formatting and structure
- Updates cross-references automatically

## Real-World Examples

### Adding New Functionality
```bash
/update-global-command ensure-local-principle add support for detecting principles in code comments, not just CLAUDE.md sections
```

**Result:** Enhances the principle detection to scan source code files for embedded guidelines and comments.

### Expanding Command Capabilities
```bash
/update-global-command session-summary include recent git commits and current branch status in summary
```

**Result:** Adds git integration to show commit history and branch information in session summaries.

### Improving Error Handling
```bash
/update-global-command add-context7-mandate validate that Context7 MCP is available before adding documentation requirements
```

**Result:** Adds pre-flight checks to ensure the required MCP server is accessible before modifying CLAUDE.md files.

### Adding New Usage Patterns
```bash
/update-global-command commit-smart support conventional commit types: docs, style, refactor, test, chore, build, ci
```

**Result:** Expands commit message generation to support the full conventional commits specification.

## Update Types Supported

### Functional Enhancements
- Add new capabilities to existing commands
- Integrate with additional tools or services
- Expand input/output handling
- Improve processing logic

### Documentation Updates
- Add new usage examples
- Update integration workflows
- Expand troubleshooting sections
- Include new best practices

### Error Handling Improvements
- Add validation steps
- Improve error messages
- Include fallback behaviors
- Add recovery procedures

### Workflow Integration
- Connect with other commands
- Add workspace integration features
- Update file handling patterns
- Improve user experience flows

## Before and After Examples

### Example 1: Enhancing ensure-local-principle

**Before:** Basic principle detection in CLAUDE.md
```markdown
## Implementation
1. Search CLAUDE.md for related keywords
2. Display existing content or add new principle
```

**Update Command:**
```bash
/update-global-command ensure-local-principle add support for scanning all .md files in project root, not just CLAUDE.md
```

**After:** Enhanced principle detection across multiple files
```markdown
## Implementation
1. Search CLAUDE.md and all .md files in project root
2. Use intelligent keyword matching across all documentation
3. Display existing content from any found location
4. Add new principle to most appropriate file
```

### Example 2: Expanding session-summary

**Before:** Basic session progress tracking
```markdown
## Response Format
- Problem description
- Actions taken
- Current status
- Next steps
```

**Update Command:**
```bash
/update-global-command session-summary include git status, recent commits, and todo progress in summary
```

**After:** Comprehensive session and project status
```markdown
## Response Format
- Problem description
- Actions taken
- Git status and recent commits
- Todo list progress
- Current status
- Next steps
```

## Advanced Features

### Workspace Synchronization
- Automatically locates workspace documentation in any subdirectory
- Updates both files with consistent information
- Maintains proper categorization and organization
- Preserves cross-references and integration notes

### Content Preservation
- Keeps existing working functionality intact
- Adds new content without breaking existing patterns
- Maintains backward compatibility
- Preserves successful examples and use cases

### Change Tracking
- Documents what was updated and when
- Maintains history of command evolution
- Shows relationship between updates
- Enables rollback if needed

### Validation and Testing
- Ensures updated commands maintain proper structure
- Validates markdown formatting
- Checks for consistency between files
- Confirms successful file updates

## Use Cases

### Command Evolution
```bash
# Start with basic functionality
/add-command-global simple git status checker

# Enhance with new features
/update-global-command git-status-checker add branch comparison and upstream tracking

# Add error handling
/update-global-command git-status-checker handle cases where git repo doesn't exist
```

### Team Collaboration
```bash
# Add team-specific features to existing commands
/update-global-command commit-smart add team member tagging in commit messages

# Integrate with team tools
/update-global-command session-summary post summaries to team Slack channel
```

### Workflow Optimization
```bash
# Connect commands together
/update-global-command ensure-local-principle automatically update related commands when principles change

# Add automation features
/update-global-command add-context7-mandate auto-run after package.json changes
```

## Integration with Command Ecosystem

### Works With All Existing Commands
- Any command created with `/add-command-global`
- All workspace-documented commands
- Legacy commands can be enhanced and documented
- Cross-command relationships are maintained

### Maintains Workspace Structure
- Preserves existing categorization
- Updates related documentation automatically
- Maintains consistent formatting across all commands
- Supports command library evolution

### Enables Continuous Improvement
- Commands can evolve based on usage experience
- New patterns can be applied to existing commands
- Best practices can be backported to older commands
- Command library stays current and relevant

---

*This command ensures your Claude Code command library remains dynamic, up-to-date, and fully synchronized between execution logic and documentation.*