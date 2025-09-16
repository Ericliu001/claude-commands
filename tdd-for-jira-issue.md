# Test-Driven Development Workflow for JIRA Issue.

**JIRA Issue:** $ARGUMENTS

## Overview
This workflow takes a JIRA Issue ID and creates test cases.

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


## Step 2: 🧭 Plan & Design Tests (Planning Only - No Code Changes)

**Command Prompt:**
```
> Claude, think [LEVEL] and create a comprehensive TDD test plan
> Focus on test cases, edge cases, and expected behaviors
```

**Thinking Levels (choose based on complexity):**
| Level | Use Case |
|-------|----------|
| `think` | Simple, well-understood tasks |
| `think hard` | Moderate complexity, some unknowns |
| `think harder` | Complex tasks with dependencies |
| `ultrathink` | Critical systems, high complexity |

**Required Test Plan Components:**
- [ ] **Feasibility Check:** Requirements testable? (stop if not)
- [ ] **Test Categories:** Unit, integration, edge cases identified
- [ ] **Test Framework:** Existing testing tools and patterns
- [ ] **Test Cases:** Detailed scenarios and expected outcomes
- [ ] **Mock Strategy:** External dependencies and data fixtures
- [ ] **File Impact:** Test files to create/modify
- [ ] **Risk Assessment:** Testing assumptions and challenges

**Test Case Planning Template:**
```
Test Category: [Unit/Integration/Edge Case]
Function/Feature: [What's being tested]
Scenario: [Specific condition/input]
Expected Result: [What should happen]
Mock Requirements: [Dependencies to mock]
```


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
4. **Confirmation:** Once approved, confirm: "I'll create test cases for [JIRA Issue]"

**Possible Outcomes:**
- ✅ **Approved:** Proceed to Step 4
- 🔄 **Modifications Needed:** Update plan, re-present
- ❌ **Rejected:** Return to Step 2 or clarify requirements


## Step 4: 💻 Implement TDD Tests (Red Phase)

**Command Prompt:**
```
> Create git branch: feature/[task-description]
> Implement unit tests with clear behavioral expectations
> Run tests to verify RED phase (proper failures)
> Commit with message: "Add unit tests for [task description] - TDD red phase"
```

**TDD Implementation Process:**
1. **Branch Creation:** `git checkout -b feature/[descriptive-name]`
2. **Test Implementation:** Write failing tests first
3. **Red Phase Validation:** Verify tests fail as expected
4. **Commit Tests:** Save failing tests to git

**Test Implementation Checklist:**
- [ ] **Test Structure:** Follow project's testing conventions
- [ ] **Clear Naming:** Descriptive test function names
- [ ] **Behavioral Comments:** Explain what behavior is being tested
- [ ] **Edge Cases:** Include boundary and error conditions
- [ ] **Mocking Setup:** Mock external dependencies appropriately
- [ ] **Assertions:** Clear, specific expected outcomes
- [ ] **Red Phase:** Tests fail with meaningful error messages

**TDD Best Practices:**
- **One Test at a Time:** Implement incrementally
- **Descriptive Names:** `test_should_return_error_when_input_is_null()`
- **AAA Pattern:** Arrange → Act → Assert structure
- **Clear Failures:** Error messages should guide implementation
- **Mock Wisely:** Mock external dependencies, not internal logic

**Quality Gates:**
- Tests compile without syntax errors
- Tests fail with clear, expected error messages
- Test names clearly describe expected behavior
- No implementation code written yet (pure TDD red phase)

**Git Workflow:**
```bash
git checkout -b feature/[issue-description]
# Write tests
# Run tests (expect failures)
git add . && git commit -m "Add unit tests for [description] - TDD red phase"
```

---

## 🧩 TDD Best Practices & Success Factors

### 🎯 Critical Success Factors
- **Sequential Execution:** Steps 1-3 are mandatory—skipping leads to poor test design
- **Red Phase First:** Always write failing tests before any implementation
- **Meaningful Failures:** Tests should fail for the right reasons with clear messages
- **Incremental Testing:** One test case at a time, building complexity gradually

### 🔴 TDD Red Phase Excellence
| Practice | Why It Matters |
|----------|----------------|
| **Write failing tests first** | Ensures tests actually test the intended behavior |
| **Verify meaningful failures** | Confirms tests will catch real bugs |
| **Clear error messages** | Guides implementation and debugging |
| **One failing test at a time** | Maintains focus and reduces complexity |

### ⚠️ Common TDD Pitfalls
| Pitfall | Prevention Strategy |
|---------|-------------------|
| Writing tests after implementation | Strict red-first discipline |
| Tests that don't fail meaningfully | Always verify failure messages |
| Over-mocking internal logic | Mock only external dependencies |
| Vague test names | Use descriptive, behavioral naming |
| Testing implementation details | Focus on behavior, not internals |

### 💡 TDD Pro Tips
- **Test Names as Documentation:** `should_throw_error_when_user_not_found()`
- **AAA Pattern:** Arrange setup, Act on system, Assert outcomes
- **Fast Feedback Loop:** Keep tests quick and focused
- **Refactor Tests Too:** Apply clean code principles to test code
- **Triangulation:** Add multiple test cases to drive generic solutions
- **Red-Green-Refactor:** Complete the full cycle before moving on

### 🧪 Test Quality Indicators
- Tests have descriptive, behavior-focused names
- Each test verifies one specific behavior
- Test failures provide clear guidance for implementation
- Tests are isolated and don't depend on each other
- External dependencies are properly mocked
