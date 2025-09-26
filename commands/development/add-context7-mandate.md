# Add Context7 Documentation Mandate Command

## Purpose
Adds mandatory Context7 documentation lookup instructions to any project's CLAUDE.md file.

## Command

```bash
# Add to project's CLAUDE.md
cat << 'EOF' >> CLAUDE.md

## 📚 MANDATORY DOCUMENTATION-FIRST RESEARCH FRAMEWORK

### 🚨 MANDATORY RESEARCH PRIORITY
**For ANY external tool, package, library, or framework:**

1. **Context7 MCP (REQUIRED FIRST)** - Always use before any implementation:
   ```bash
   mcp__context7__resolve-library-id("package-name")
   mcp__context7__get-library-docs("/org/package-name")
   ```
2. **Version-Specific Official Documentation** - Only if Context7 unavailable
3. **Project Codebase Patterns** - Search for existing implementations
4. **Cross-Reference Multiple Sources** - Verify accuracy and compatibility

### 📖 VERSION-SPECIFIC DOCUMENTATION STRATEGY
- **Always check package versions first** (\`package.json\`, requirements files)
- **Use exact version documentation** to avoid compatibility issues
- **Read migration guides** for major version changes
- **Test examples** against actual package behavior

### ⚠️ MANDATORY COMPLIANCE
- **NEVER implement external libraries** without Context7 research first
- **ALWAYS verify version compatibility** with project dependencies
- **DOCUMENT reasoning** when Context7 docs are unavailable
- **CROSS-REFERENCE** Context7 findings with official docs

EOF
```

## Usage Examples

### Add to existing project
```bash
cd /path/to/project
# Run the command above to append Context7 mandate
```

### Verify it was added
```bash
tail -30 CLAUDE.md | grep -A 5 "MANDATORY DOCUMENTATION-FIRST"
```

### For new projects (integrate with setup)
```bash
# Copy template first
cp ~/.claude/workspace/templates/CLAUDE.md ./CLAUDE.md

# Add Context7 mandate
# [run command above]
```

## Benefits
- ✅ **Prevents hallucinations** by mandating documentation lookup
- ✅ **Ensures version compatibility** with package.json
- ✅ **Standardizes research approach** across all projects
- ✅ **Reduces debugging time** from incorrect assumptions
- ✅ **Enforces best practices** automatically

## Integration with Workspace

This command should be part of the standard new-project workflow:

1. Copy base CLAUDE.md template
2. **Add Context7 mandate** (this command)
3. Customize for project-specific needs
4. Set up local git ignore

## Validation

After adding, verify Claude follows the mandate:
- Ask Claude to implement any external library
- Confirm it uses Context7 first
- Check it verifies versions with package.json