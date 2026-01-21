# Create Issues in Linear

Create issues in Linear from the provided description.

## Input

$ARGUMENTS

## Instructions

### 1. Validate Input

If `$ARGUMENTS` is empty, ask the user which tasks they want to create.

### 2. Select Team

Use `mcp__linear__list_teams` to list available teams.

Ask the user which team to use (unless already specified in the input).

### 3. Parse Issues

Analyze the input and extract the issues to be created. Input can be:

- Free text describing multiple tasks
- Bulleted or numbered list
- A single task

For each identified issue, extract or infer:

- **title** (required): Concise task title
- **description** (optional): Additional details in Markdown
- **priority** (optional): 0=No priority, 1=Urgent, 2=High, 3=Normal, 4=Low
- **labels** (optional): Existing labels in Linear
- **assignee** (optional): User to assign (use "me" for the current user)
- **dueDate** (optional): Due date in ISO format

### 4. Confirm with User

Before creating, show a summary of the issues to be created:

```
## Issues to create in team [TEAM_NAME]:

1. **[Title 1]**
   - Priority: [X]
   - Labels: [X, Y]

2. **[Title 2]**
   - Description: [summary]
```

Request confirmation before proceeding.

### 5. Create Issues

For each confirmed issue, use `mcp__linear__create_issue` with the extracted fields.

### 6. Return Result

After creating all issues, return a list with:

- Identifier (e.g., `TEAM-123`)
- Title
- Issue URL

Example output:

```
## Issues created:

- [TEAM-123](url): Issue title 1
- [TEAM-124](url): Issue title 2
```

## Usage Examples

- `/linear-create-issue create health check endpoint and add unit tests`
- `/linear-create-issue 1. Refactor module X 2. Document API Y`
- `/linear-create-issue` (no arguments - will ask)
