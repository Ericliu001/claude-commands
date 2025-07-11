Please solve the problem: $ARGUMENTS.


# Claude Code Workflow: Explore → Plan → Discuss → Code → Test → Commit


## Step 1: 🧠 Explore (Don't Code Yet)

**Command Prompt:**
> Use subagents to read the relevant files — but **do not write any code yet**.

**Optional:**
> Use subagents to investigate any unclear relationships or dependencies.

**Key Activities:**
- Understand existing code structure and patterns
- Identify dependencies and integrations
- Look for existing similar implementations
- Note testing frameworks and conventions

- ⚠️ **Critical:** Avoid asking for implementation at this stage.


## Step 2: 🧭 Plan (Think Before Coding)

**Command Prompt:**
> Claude, **think harder** and develop a plan. Outline each step clearly.

**Choose your thinking level based on complexity:**
- `think` - Simple, well-understood tasks
- `think hard` - Moderate complexity with some unknowns
- `think harder` - Complex tasks with dependencies
- `ultrathink` - Highly complex or critical systems

**Plan should include:**
- Implementation steps (numbered)
- Files to modify/create
- Testing approach
- Potential risks/assumptions
- Rollback strategy if needed

## Step 3: 🗣️ Discuss & Validate

**Command Prompt:**
> Present your plan to me and ask: "Does this approach look good? Any concerns or modifications before I proceed?"

> **Wait for my response before continuing to Step 4.**

**Discussion Points:**
- Review implementation steps
- Validate assumptions
- Confirm testing approach
- Address any concerns or edge cases
- Get approval to proceed

## Step 4: 💻 Code (Verify While Implementing)

**Command Prompt:**
> Create a new git branch and give it a branch name.
> Now implement the plan step by step. As you write, verify each part is consistent with the surrounding code.

**Implementation Guidelines:**
- Follow existing code patterns and conventions
- Implement incrementally (one logical piece at a time)
- Verify each change works with surrounding code
- Handle error cases appropriately
- Add necessary logging/debugging

**Stop Points:**
- After core implementation (before tests)
- If you encounter unexpected issues
- If assumptions prove incorrect


## Step 5: 🧪 Test & Validate

**Command Prompt:**
> Run existing tests to ensure no regressions. Add new tests if needed based on project conventions.

**Testing Activities:**
- Run relevant test suites
- Add unit tests for new functionality
- Test edge cases and error conditions
- Verify integration with existing systems
- Manual testing if appropriate

## Step 6: 📦 Commit 

**Command Prompt:**
> Git commit the changes and generate commit message summarizing what you've done.

**Commit Guidelines:**
- Use conventional commit format if project uses it
- Include both what and why in commit message
- Reference any issues or tickets
- Ensure all changes are staged



---

## 🧩 Notes & Best Practices

**Critical Success Factors:**
- Steps **1, 2, and 3 are critical**. Skipping them leads to premature coding without sufficient context.
- Use subagents generously during exploration to preserve context and depth of reasoning.
- Save plans early—resetting to a well-defined plan checkpoint is easier than unwinding bad code.

**Common Pitfalls to Avoid:**
- Rushing to implementation without understanding existing patterns
- Ignoring error handling and edge cases
- Not testing thoroughly before committing
- Making assumptions without validation

**Recovery Strategies:**
- If stuck, return to exploration phase with new questions
- If tests fail, iterate on implementation before committing
- If plan proves flawed, restart from Step 2 with new insights