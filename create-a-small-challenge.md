Requirements: $ARGUMENTS.


# Claude Code Workflow: Explore → Plan & Breakdown → Discuss → Create Unit Tests → Commit
This workflow is to take requirements and break them down to small tasks, and then let me choose one task to implement and you will generate unit tests accordingly.


## Step 1: 🧠 Explore (Don't Code Yet)

**Command Prompt:**
> Check the feasibilities of the requirements, stop and ask questions if needed.
> Use subagents to read the relevant files — but **do not write any code yet**.


**Optional:**
> Use subagents to investigate any unclear relationships or dependencies.

**Key Activities:**
- Verify the feasibilities of the requirements with the current tech stack, if not feasible, stop and ask me to change requirements or tech stack.
- Understand existing code structure and patterns
- Identify dependencies and integrations
- Look for existing similar implementations
- Note testing frameworks and conventions

- ⚠️ **Critical:** Avoid asking for implementation at this stage.


## Step 2: 🧭 Plan & Breakdown (Think, Don't Code Yet)

**Command Prompt:**
> Claude, **think harder** and develop a plan that consists of tasks, each task should take no more than 2 hours to implement.

**Choose your thinking level based on complexity:**
- `think` - Simple, well-understood tasks
- `think hard` - Moderate complexity with some unknowns
- `think harder` - Complex tasks with dependencies
- `ultrathink` - Highly complex or critical systems

**Plan should include:**
- Verify the feasibilities of the requirements, if not feasible, stop and ask me to change requirements.
- List tasks (numbered), each task should take no more than 2 hours to complete.
- Files to modify/create
- Testing approach
- Potential risks/assumptions
- Rollback strategy if needed

## Step 3: 🗣️ Discuss & Validate (Stop and wait for my response before proceeding to the next step)

**Command Prompt:**
> Present your plan to me and ask: "Does this approach look good? Which task would you like to begin with?"

> **Wait for my response before continuing to Step 4.**

**Discussion Points:**
- Review tasks
- Confirm my choice of task
- Validate assumptions
- Confirm testing approach
- Address any concerns or edge cases
- Stop here and Wait for my approval and choices of task to proceed
- Remember my choice of task.

## Step 4: 💻 Create Unit Tests

**Command Prompt:**
> Based on my choice of the task, create a new git branch and give it a branch name based on the task description.
> Then create unit tests for the task I chose, with clear comments explaining expected behavior.
> Run the tests to ensure they fail appropriately (since implementation doesn't exist yet).
> Create a git commit when all unit tests.

**Implementation Guidelines:**
- Each unit test should have clear comments on the expectations
- Follow existing code patterns and conventions
- Implement unit tests incrementally (testing one logical piece at a time)
- Verify each change would work with surrounding code
- Handle error cases appropriately
- Tests should fail initially (red phase of TDD)
- Commit the unit tests to Git

**Stop Points:**
- After core unit tests creation and validation
- If you encounter unexpected issues
- If assumptions prove incorrect

## Step 5: 🚀 Implementation (My Task)

**Command Prompt:**
> Present the task detail and expectations then tell me: "You can start the implementation now."
> Only help me with implementations when I run into problems and ask for help.

**Your Responsibility:**
> Answer my questions.
> Only help me with implementations when I ask you to do so.

**My Responsibility:**
> Now let me implement the actual code to make the tests pass. This is the "green" phase of TDD.

**Guidelines:**
- Run tests frequently to check progress
- Allow me to implement incrementally - make one test pass at a time
- Follow the test specifications exactly
- Suggest refactorings as needed


**Success Criteria:**
- All unit tests pass
- Code follows existing patterns and conventions
- No linting or type errors

## Step 6: 📦 Final Commit

**Command Prompt:**
> Once I confirm all tests are passing and the implementation is complete, create a final commit with the implementation.

**Commit Guidelines:**
- Use conventional commit format if project uses it
- Include both what and why in commit message
- Reference any issues or tickets
- Run linting and type checking before commit
- Ensure all changes are staged



---

## 🧩 Notes & Best Practices

**Critical Success Factors:**
- Steps **1, 2, and 3 are critical**. Skipping them leads to premature coding without sufficient context.
- Use subagents generously during exploration to preserve context and depth of reasoning.
- Save plans early—resetting to a well-defined plan checkpoint is easier than unwinding bad code.
- Clear handoff between Claude (tests) and user (implementation) is essential.

**Common Pitfalls to Avoid:**
- Rushing to implementation without understanding existing patterns
- Ignoring error handling and edge cases  
- Not running tests frequently during implementation
- Making assumptions without validation
- Claude implementing code instead of just creating tests

**Recovery Strategies:**
- If stuck during exploration, return to Step 1 with new questions
- If tests are poorly designed, Claude should refactor them before handoff
- If implementation gets complex, break task into smaller subtasks
- If plan proves flawed, restart from Step 2 with new insights

**Workflow Completion:**
- Task is complete when all tests pass and code is committed
- Consider creating follow-up tasks for remaining features
- Document any learnings or patterns discovered for future tasks