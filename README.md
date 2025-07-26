# Claude Commands

This repository contains custom commands for Claude Code to streamline common development workflows.

## Available Commands

### `/explore-plan-code`
A comprehensive workflow for solving development problems systematically.

**Usage:** `/explore-plan-code <problem description>`

**Workflow Steps:**
1. **🧠 Explore** - Understand the codebase and verify feasibility
2. **🧭 Plan** - Develop detailed implementation plan
3. **🗣️ Discuss** - Present plan and get approval
4. **💻 Code** - Implement step by step
5. **🧪 Test** - Run tests and validate changes
6. **📦 Commit** - Create git commit with proper message

**Best for:** Complex features, refactoring, bug fixes requiring careful planning

### `/fix-github-issue`
Streamlined workflow for fixing GitHub issues with proper branch management.

**Usage:** `/fix-github-issue <issue-number>`

**Process:**
1. **Get Issue Details:** Run `gh issue view <issue-number>`
2. **Execute Workflow:** Copy the complete issue output and run:
   ```
   /explore-plan-code Fix GitHub issue <issue-number>
   
   [PASTE THE COMPLETE gh issue view OUTPUT HERE]
   ```

**GitHub-specific features:**
- Uses GitHub CLI for all GitHub operations
- Creates branches with pattern: `Fix/issue.<issue-number>-name`
- Automatically pushes branch to remote after committing

**Best for:** GitHub issue resolution with proper tracking and branch management

## Installation

These commands are designed to work with Claude Code's custom command system. Place the `.md` files in your Claude commands directory, which is `~/.claude/commands`.

## Contributing

When adding new commands:
- Follow the existing naming conventions
- Include clear usage instructions
- Document the workflow steps
- Test with various scenarios
