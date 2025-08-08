GitHub issue: $ARGUMENTS.

## Step 1: Get Issue Details
Run this command first to get the complete issue information:
```bash
gh issue view $ARGUMENTS
```

## Step 2: Execute Explore-Plan-Code Process
Copy the ENTIRE output from the `gh issue view` command above, then run:

/explore-plan-code

```
[PASTE THE COMPLETE gh issue view OUTPUT HERE]
```

## Step 3: Create pull request
Create pull request on Github.

## Additional GitHub-specific requirements:
- Use the GitHub CLI (`gh`) for all GitHub-related tasks
- Create a new git branch with pattern: "Fix/issue.(issue number)-name" 
- Push the git branch to remote repository after committing
- Use gh pr create
