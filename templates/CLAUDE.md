# CLAUDE.md - Development Guidelines Template

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

[PROJECT DESCRIPTION - Replace with specific project details]

## 🚨 CRITICAL DEVELOPMENT PROTOCOLS

### ⚡ MANDATORY VALIDATION STEPS
**NEVER skip these steps after any code changes:**

```bash
# Add your project's specific validation commands
# Examples:
# npm run lint && npm run type-check
# cargo check && cargo test
# python -m mypy . && python -m pytest
```

### 🔍 CONVENTION CHECKING PROTOCOL
**Before creating ANY new code, ALWAYS check for existing patterns:**

1. **Search for existing patterns** - Use Grep tool to find similar implementations
2. **Check import statements** - Look for established patterns in similar files
3. **Examine existing architecture** - Follow established patterns for consistency
4. **Review naming conventions** - Match existing code style

#### Pattern Checking Examples:
```bash
# Search for existing patterns before creating new ones
grep -r "pattern.*Type" src/
grep -r "interface.*Config" src/
```

### 📋 CODE REUSE PRINCIPLES
- **Search before create** - Always look for existing implementations
- **Extend before replace** - Modify existing patterns rather than creating new ones
- **Import before implement** - Use existing types, utilities, shared code

### 🔧 PROJECT-SPECIFIC BEST PRACTICES

#### [FRAMEWORK] Conventions
```typescript
// Add framework-specific patterns here
// Example for React/Vue/Angular patterns
// Example for backend API patterns
// Example for database interaction patterns
```

#### Error Handling & Logging
```typescript
// Add project-specific error handling patterns
// Add logging conventions
// Add monitoring/observability patterns
```

## 📂 PROJECT STRUCTURE CONVENTIONS

### File Organization
- **[Category]**: `src/[category]/[feature]/[feature-file].ts`
- **[Tests]**: `src/[category]/[feature]/[feature].test.ts`
- **[Types]**: `src/types/[domain].ts`

### Import Order
1. Framework imports
2. Third-party libraries
3. Internal utilities/services
4. Local component imports
5. Type-only imports

### Naming Conventions
- **[Functions]**: camelCase
- **[Classes]**: PascalCase
- **[Constants]**: UPPER_SNAKE_CASE
- **[Files]**: kebab-case

## 🚨 CRITICAL ANTI-PATTERNS TO AVOID

❌ **[Add project-specific anti-patterns]**
❌ **Using `any` type (strictly forbidden)**
❌ **Skipping validation steps**
❌ **Creating duplicate implementations**

## 💡 DECISION FRAMEWORK

When facing implementation choices:

1. **Search existing codebase** for similar patterns
2. **Check framework/language best practices**
3. **Consider performance implications**
4. **Evaluate maintainability**
5. **Ensure type safety**
6. **Test with validation commands**

## 🏆 QUALITY GATES

Before completing any feature:
- [ ] All lint warnings resolved
- [ ] All type errors resolved
- [ ] Tests passing
- [ ] Existing patterns followed
- [ ] Code review completed
- [ ] Documentation updated

## Development Commands

```bash
# Development server
[ADD PROJECT COMMANDS]

# Quality checks (run after every change)
[ADD VALIDATION COMMANDS]

# Testing
[ADD TEST COMMANDS]

# Build
[ADD BUILD COMMANDS]
```

## 🚨 CRITICAL: Team Collaboration Standards

### NO AI TOOL REFERENCES
**NEVER EVER include in commits, PRs, or any team-facing content:**
- "Generated with Claude Code" or similar phrases
- "Co-Authored-By: Claude" signatures
- Any reference to AI assistance or tools
- Robot emoji (🤖) indicating AI involvement
- AI tool signatures in commit messages or documentation

All git commits, pull requests, and team communication must appear as normal human development work.

---

*This document captures critical patterns and anti-patterns discovered through development experience. Always refer to these guidelines when making implementation decisions.*