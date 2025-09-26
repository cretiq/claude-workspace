# GitHub Work Item Analysis Command

## Purpose
Comprehensively analyze GitHub issues, pull requests, or discussions using GitHub CLI and create detailed implementation plans based on current project state.

## Command Usage

```bash
/analyze-github-workitem https://github.com/owner/repo/issues/123
/analyze-github-workitem https://github.com/owner/repo/pull/456
/analyze-github-workitem https://github.com/owner/repo/discussions/789
```

## What It Does

### 1. **GitHub Data Extraction**
- Fetches complete work item details using GitHub CLI
- Retrieves comments, labels, assignees, and metadata
- Gathers file changes and code context for PRs

### 2. **Project State Analysis**
- Searches codebase for related functionality
- Reviews existing patterns and implementations
- Analyzes dependencies and compatibility requirements

### 3. **Comprehensive Planning**
- Creates detailed implementation breakdown
- Identifies risks and mitigation strategies
- Provides multiple approach options with trade-offs

### 4. **Actionable Output**
- Step-by-step task breakdown
- Testing and validation strategies
- Best practice recommendations

## Prerequisites

- GitHub CLI installed and authenticated
- Access to the target repository
- Current project directory with relevant codebase

## Example Output

The command generates a comprehensive analysis report including:

- **Work Item Overview** - Summary, status, priority
- **Technical Analysis** - Current gaps, patterns to leverage
- **Risk Assessment** - Potential issues, complexity estimation
- **Implementation Plan** - Phased approach with specific tasks
- **Testing Strategy** - Validation and quality assurance steps

## Use Cases

### 🐛 Bug Analysis
- Analyze bug reports and reproduction steps
- Identify root cause and affected components
- Create fix strategy with testing approach

### ✨ Feature Requests
- Break down feature requirements into tasks
- Identify dependencies and integration points
- Suggest implementation phases

### 🔄 Pull Request Reviews
- Analyze proposed changes and their impact
- Cross-reference with project conventions
- Provide implementation feedback

### 💬 Discussion Planning
- Convert discussions into actionable plans
- Identify technical approaches and alternatives
- Create roadmap from community input

## Integration with Workflow

### New Feature Development
1. Use this command to analyze feature requests
2. Follow the generated implementation plan
3. Use incremental development principles from CLAUDE.md
4. Apply Context7 research for any new dependencies

### Bug Fixing
1. Analyze bug reports thoroughly
2. Identify affected components and test cases
3. Implement fixes following the suggested approach
4. Validate against the generated testing strategy

### Code Reviews
1. Analyze PRs before reviewing
2. Use insights to provide meaningful feedback
3. Verify adherence to project patterns
4. Check for potential impacts on existing features

## Benefits for Development Teams

- **Reduces Planning Time** - Automated analysis and breakdown
- **Improves Quality** - Comprehensive risk assessment
- **Ensures Consistency** - Leverages existing codebase patterns
- **Facilitates Collaboration** - Clear, actionable plans for team members
- **Minimizes Surprises** - Identifies potential issues early

## Advanced Features

- **Context-Aware** - Understands project-specific patterns
- **Multi-Source** - Combines GitHub data with local codebase analysis
- **Risk-Conscious** - Proactively identifies potential problems
- **Alternative Approaches** - Presents multiple implementation options
- **Testing-Focused** - Includes validation strategies in all plans

---

*This command transforms GitHub work items into actionable development plans, ensuring thorough analysis and strategic implementation.*