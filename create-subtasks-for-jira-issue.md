# Create JIRA Sub-tasks Workflow

**JIRA Issue:** $ARGUMENTS

## Overview
This workflow takes a JIRA Issue ID and systematically breaks it down into manageable sub-tasks of 2 hours or less each.

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


## Step 2: 🧭 Plan & Breakdown (Planning Only - No JIRA Changes)

**Command Prompt:**
```
> Claude, think [LEVEL] and create a detailed breakdown plan
> Each task must be ≤ 2 hours implementation time
```

**Thinking Levels (choose based on complexity):**
| Level | Use Case |
|-------|----------|
| `think` | Simple, well-understood tasks |
| `think hard` | Moderate complexity, some unknowns |
| `think harder` | Complex tasks with dependencies |
| `ultrathink` | Critical systems, high complexity |

**Required Plan Components:**
- [ ] **Feasibility Check:** Requirements achievable? (stop if not)
- [ ] **Task List:** Numbered, ≤2 hours each
- [ ] **File Impact:** Files to modify/create
- [ ] **Testing Strategy:** Approach and frameworks
- [ ] **Risk Assessment:** Assumptions and potential issues
- [ ] **Rollback Plan:** Recovery strategy if needed

**Task Breakdown Template:**
```
Task #: [Brief Title]
- Estimated Time: [X hours]
- Files: [list of files]
- Description: [what will be done]
- Dependencies: [other tasks/external deps]
```

## Step 3: 🗣️ Discuss & Validate ⏸️ **MANDATORY STOP POINT**

**Command Prompt:**
```
> Present your plan and ask: "Does this approach look good?"
> WAIT for user response before continuing to Step 4
```

**🛑 Critical:** Do NOT proceed without explicit user approval

**Validation Process:**
1. **Plan Review:** Present complete breakdown
2. **Assumption Check:** Highlight key assumptions
3. **User Input:** Wait for feedback/modifications
4. **Confirmation:** Once approved, confirm: "I'll create tasks for [JIRA Issue]"

**Possible Outcomes:**
- ✅ **Approved:** Proceed to Step 4
- 🔄 **Modifications Needed:** Update plan, re-present
- ❌ **Rejected:** Return to Step 2 or clarify requirements

**Task Refinement Guidelines:**
- Combine/split tasks as requested
- Ensure final tasks remain ≤2 hours
- Maintain clear, actionable descriptions
- Update dependencies accordingly

## Step 4: 💻 Create JIRA Sub-tasks

**Command Prompt:**
```
> Create sub-tasks using JIRA CLI (`jira`)
> Each sub-task: clear summary + description, ≤2 hours
```

**Sub-task Creation Checklist:**
- [ ] **Summary:** Clear, actionable title
- [ ] **Description:** Detailed requirements and acceptance criteria
- [ ] **Time Estimate:** Realistic ≤2 hour estimate
- [ ] **Links:** Parent issue properly linked
- [ ] **Labels/Components:** Appropriate categorization


**Quality Standards:**
- Actionable summaries (start with verbs)
- Specific acceptance criteria
- Technical context when needed
- Clear dependencies noted

---

## 🧩 Best Practices & Success Factors

### 🎯 Critical Success Factors
- **Sequential Execution:** Steps 1-3 are mandatory—skipping leads to poor context
- **Generous Subagent Use:** Preserve reasoning depth during exploration
- **Early Plan Saves:** Checkpoint well-defined plans before implementation
- **Clear Handoffs:** Maintain clarity between planning and execution phases

### ⚠️ Common Pitfalls to Avoid
| Pitfall | Prevention Strategy |
|---------|-------------------|
| Rushing to implementation | Complete Steps 1-3 thoroughly |
| Missing existing patterns | Deep codebase exploration |
| Assumption without validation | Explicit feasibility checks |
| Ignoring edge cases | Comprehensive testing strategy |
| Overly complex tasks | Strict 2-hour time limit |

### 💡 Pro Tips
- **Think Levels:** Match thinking complexity to task difficulty
- **Task Granularity:** Aim for 1.5-2 hour tasks (allows buffer)
- **Clear Descriptions:** Write sub-tasks like you're handing them off
- **Dependency Mapping:** Identify task interdependencies early
- **Rollback Ready:** Always have an undo plan
