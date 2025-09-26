# Update Incremental Development Principles Command

## Purpose
Adds comprehensive incremental development methodology to any project's CLAUDE.md file, promoting best practices for small increments, simplicity, and clean code.

## Generated From
**Meta-command input:** `update/append to local claude md file (memory) that we want to work in best practice ways with small increments and way of working should be simple approach, less is more, and use clean code`

## Command Usage

```bash
/update-incremental-principles
```

## What It Adds

This command appends a complete methodology section to your project's CLAUDE.md covering:

### Core Principles
- **Small Increments Philosophy** - Work in manageable chunks with frequent validation
- **Simple Approach Mandate** - Always choose the straightforward solution first
- **Less is More Principle** - Focus on core value, remove before adding
- **Clean Code Standards** - Readable, maintainable code practices

### Implementation Workflow
A 6-step process for applying incremental development:
1. Define smallest possible increment
2. Implement using simplest approach
3. Test and validate immediately
4. Refactor for clarity
5. Ship or integrate
6. Plan next step

### Quality Gates & Anti-Patterns
- Production-ready requirements for every increment
- Common pitfalls to avoid (big bang implementations, premature optimization, etc.)
- Testing and documentation standards

## Use Cases

### New Projects
```bash
# Set up project with base CLAUDE.md first
cp ~/.claude/workspace/templates/CLAUDE.md ./CLAUDE.md

# Add incremental development principles
/update-incremental-principles
```

### Existing Projects
```bash
# Navigate to project directory
cd /path/to/your/project

# Add methodology to existing CLAUDE.md
/update-incremental-principles
```

### Team Onboarding
Use this command to ensure all project repositories have consistent development methodology documented.

## Integration with Other Commands

Works well with:
- `/add-context7-mandate` - Technical documentation standards
- `/commit-smart` - Incremental commit practices
- `/session-summary` - Progress tracking alignment

## Customization

After adding the base methodology:
1. Review the principles with your team
2. Adapt specific practices to your project context
3. Add project-specific examples
4. Integrate with existing development workflows

## Benefits

**For Developers:**
- Clear guidance on how to approach feature development
- Reduced complexity and stress through small increments
- Improved code quality through built-in practices

**For Teams:**
- Consistent development approach across projects
- Better collaboration through shared methodology
- Faster delivery through incremental releases

**For Projects:**
- Higher quality, maintainable codebase
- Reduced risk through frequent validation
- Better user feedback integration

## Example Output

The command adds a structured methodology section including:

```markdown
## 🎯 INCREMENTAL DEVELOPMENT METHODOLOGY

### ⚡ CORE DEVELOPMENT PRINCIPLES
[Detailed principles and practices]

### 🔄 IMPLEMENTATION WORKFLOW
[Step-by-step process]

### ⚠️ ANTI-PATTERNS TO AVOID
[Common mistakes and how to avoid them]

### 📋 QUALITY GATES
[Standards and requirements]
```

## Maintenance

### Regular Updates
- Review methodology quarterly for effectiveness
- Update based on team feedback and learnings
- Adapt principles as project complexity grows

### Project-Specific Adaptations
- Add examples relevant to your technology stack
- Include team-specific practices and standards
- Reference project-specific tools and processes

---

*This command embodies the meta-command generator's ability to transform natural language requirements into actionable development practices, making methodology adoption effortless and consistent.*