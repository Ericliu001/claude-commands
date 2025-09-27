# Analyze a JIRA Issue.

**JIRA Issue:** $ARGUMENTS

## Overview
This workflow takes a JIRA Issue ID and analyzes it and provides context.

**Required Tools:**
- JIRA CLI (`jira`) - [Documentation](https://github.com/Ericliu001/hello_python/blob/main/PythonPrograms/jira_interactions/cli/README.md)
- GitHub CLI (`gh`) - For GitHub-related tasks


## Step 1: 🧠 Explore (Analysis Only - No Coding)

**Primary Actions:**
```
> Read requirements from the JIRA issue
> Get parent and sibling issue context
> Assess technical feasibility with current stack
> Use subagents for codebase exploration (NO code changes)
```

**Exploration Checklist:**
- [ ] JIRA issue requirements understood
- [ ] Parent/sibling issue context reviewed
- [ ] Technical feasibility confirmed (stop if not feasible)
- [ ] Existing code patterns identified
- [ ] Dependencies and integrations mapped
- [ ] Testing frameworks and conventions noted
- [ ] Similar implementations found (if any)

**Optional Deep-Dive:**
> Investigate unclear relationships or complex dependencies using subagents

⚠️ **Critical Rule:** NO implementation discussions or code changes at this stage


## Step 2: 🧭 Plan (Planning Only - No Code Changes)

**Command Prompt:**
```
> Claude, think [LEVEL] and create a comprehensive implementation plan
> Explore alternative approaches if available
> Focus on edge cases, and expected behaviors
```

**Thinking Levels (choose based on complexity):**
| Level | Use Case |
|-------|----------|
| `think` | Simple, well-understood tasks |
| `think hard` | Moderate complexity, some unknowns |
| `think harder` | Complex tasks with dependencies |
| `ultrathink` | Critical systems, high complexity |


## Step 3: 💻 Comment on JIRA Issue

**Command Prompt:**
```
> Add a comment to the JIRA issue which includes the plan and all the information you've found.
> (If applicable) The comment should also include code examples in markdown.
> Including: Implementation details, (if available) alternative approaches, scope and time estimation of this implementation
```
