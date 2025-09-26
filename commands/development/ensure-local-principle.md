# Ensure Local Principle Command

## Purpose
Intelligently analyzes and maintains principles in project CLAUDE.md files. Ensures specific rules, guidelines, and preferences exist and are properly documented in your project's memory file.

## Generated From
**Meta-command input:** `a command that will analyze the local (repo) claude md file and make sure whatever after /verify-local-memory ... always use gh cli instead of calling the address`

## Command Usage

```bash
/ensure-local-principle {your principle or guideline}
```

## How It Works

### 1. Smart Analysis
- Searches existing CLAUDE.md for related content using fuzzy matching
- Understands context and synonyms (e.g., "gh cli" = "GitHub CLI" = "use gh")
- Identifies existing principles that match your intent

### 2. Intelligent Response
**If principle EXISTS:**
- Shows the exact existing snippet from CLAUDE.md
- Confirms no update is needed
- Maintains consistency without duplication

**If principle DOESN'T EXIST:**
- Interprets your natural language intent
- Generates well-structured, actionable content
- Adds it to the appropriate section in CLAUDE.md

### 3. Smart Categorization
Automatically organizes principles into logical sections:
- **🛠️ Tool Preferences** - CLI tools, preferred libraries, development tools
- **📏 Code Standards** - Coding conventions, style guides, best practices
- **🔄 Workflow Rules** - Process guidelines, review requirements, deployment practices
- **📋 Quality Gates** - Testing requirements, validation standards

## Real-World Examples

### GitHub CLI Preference
```bash
/ensure-local-principle always use gh cli instead of web interface for repo operations
```

**If found:** Shows existing GitHub CLI guidelines
**If not found:** Adds structured section about preferring CLI over web interface

### TypeScript Standards
```bash
/ensure-local-principle prefer TypeScript over JavaScript for all new components
```

**Generates:**
```markdown
## 📏 CODE STANDARDS & CONVENTIONS

### Language Preferences
- **Use TypeScript for all new components** - Prefer TypeScript over JavaScript for better type safety and developer experience
- **Why:** Better tooling, compile-time error detection, improved refactoring support
- **Examples:**
  - New React components: `.tsx` files
  - Utility functions: `.ts` files
  - Gradual migration from existing `.js` files
```

### Testing Requirements
```bash
/ensure-local-principle all new functions need unit tests with minimum 80% coverage
```

**Generates organized testing standards with coverage requirements and examples**

## Use Cases

### New Project Setup
```bash
# Establish core development principles
/ensure-local-principle use semantic commit messages
/ensure-local-principle require peer review for all PRs
/ensure-local-principle prefer small, focused functions
```

### Team Onboarding
```bash
# Ensure consistent tool usage
/ensure-local-principle always use pnpm instead of npm
/ensure-local-principle use ESLint with Prettier for code formatting
/ensure-local-principle follow conventional commits specification
```

### Legacy Project Improvement
```bash
# Document existing practices
/ensure-local-principle migrate to React hooks from class components
/ensure-local-principle use CSS modules for component styling
/ensure-local-principle implement error boundaries for better UX
```

### Quality Assurance
```bash
# Enforce quality standards
/ensure-local-principle no console.log in production code
/ensure-local-principle validate props with TypeScript interfaces
/ensure-local-principle write integration tests for API endpoints
```

## Integration Workflow

### With Other Commands
- **After `/add-context7-mandate`** - Add tool-specific research requirements
- **Before `/commit-smart`** - Establish commit message standards
- **With `/update-documentation`** - Keep principles and docs in sync

### Project Lifecycle Integration
1. **Project Start:** Establish core principles and tool preferences
2. **Development:** Add specific coding standards as needs arise
3. **Team Growth:** Document implicit practices for new team members
4. **Maintenance:** Update principles as technology and practices evolve

## Advanced Features

### Intelligent Content Generation
The command doesn't just add raw text—it creates structured, actionable content:

**Input:** "always use gh cli"
**Generated:**
- Clear principle statement
- Reasoning behind the preference
- Specific command examples
- When to use vs. alternatives

### Fuzzy Matching Examples
- "eslint" finds existing "ESLint", "linting", "code quality" sections
- "react hooks" matches "hooks", "functional components", "React patterns"
- "testing" finds "tests", "unit testing", "coverage", "QA" content

### Context-Aware Additions
- Detects existing section structure
- Maintains consistent formatting and emoji usage
- Groups related principles together
- Avoids creating duplicate or conflicting guidelines

## Maintenance Tips

### Regular Auditing
```bash
# Periodically review principles for relevance
/ensure-local-principle remove outdated practices from CLAUDE.md
```

### Team Synchronization
- Use in team meetings to establish shared standards
- Run on existing projects to document implicit practices
- Update principles as technology stacks evolve

### Project-Specific Customization
- Add examples relevant to your specific codebase
- Include team-specific tools and preferences
- Reference project-specific standards and requirements

---

*This command transforms natural language guidelines into structured, actionable project principles, making implicit team knowledge explicit and maintainable.*