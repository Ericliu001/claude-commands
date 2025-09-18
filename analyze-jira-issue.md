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


## Step 3: 🗣️ Discuss & Validate ⏸️ **MANDATORY STOP POINT**

**Command Prompt:**
```
> Present your plan and ask: "Does this approach look good?"
> WAIT for user response before continuing to Step 4
```

**🛑 Critical:** Do NOT proceed without explicit user approval

**Validation Process:**
1. **Plan Review:** Present complete plan
2. **Assumption Check:** Highlight key assumptions
3. **User Input:** Wait for feedback/modifications
4. **Confirmation:** Once approved, confirm: "I'll update [JIRA Issue]"

**Possible Outcomes:**
- ✅ **Approved:** Proceed to Step 4
- 🔄 **Modifications Needed:** Update plan, re-present
- ❌ **Rejected:** Return to Step 2 or clarify requirements


## Step 4: 💻 Comment on JIRA Issue

**Command Prompt:**
```
> Add a comment to the JIRA issue which includes the all the information you've found.
> Including: Implementation details, (if available) alternative approaches, scope and time estimation of this implementation
```
