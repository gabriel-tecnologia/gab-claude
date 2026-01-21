# List Issues for a Person

List all issues assigned to a specific person in Linear.

## Input

$ARGUMENTS

## Instructions

### 1. Identify Assignee

- If `$ARGUMENTS` is empty:
  1. Use `mcp__linear__get_user` with `query: "me"` to get the current user
  2. Use the returned email as the assignee filter
- If `$ARGUMENTS` is provided, use the value as filter (name or email)

### 2. Fetch Issues

Use `mcp__linear__list_issues` with:

- `assignee`: value identified in step 1
- `limit`: 50 (or more if necessary)

**IMPORTANT**: Ignore issues with state "Completed", "Done", "Canceled" or "Cancelled". Show only active issues.

### 3. Sort and Display Result

**Row ordering** (in this priority order):

1. **Team** (alphabetical)
2. **Status** (In Progress > In Review > Refinement > Detailing > Planned > Todo > Backlog > Idea)
3. **Priority** (Urgent > High > Medium > Low > no priority)
4. **Due Date** (with date first, without date last)
5. **Title** (alphabetical)

**Format** (single table with sorted issues):

# Issues for [PERSON_NAME]

| Team | Status      | Priority | Due Date   | Title              | Labels | URL |
| ---- | ----------- | -------- | ---------- | ------------------ | ------ | --- |
| AAA  | In Progress | High     | 2025-01-25 | AAA-10 Issue title | Label1 | url |
| AAA  | Todo        | Medium   | -          | AAA-20 Issue title | Label2 | url |
| BBB  | In Progress | High     | -          | BBB-15 Issue title | -      | url |

**Columns:**

- Team: team abbreviation
- Status: current state
- Priority: if not defined, use `-`
- Due Date: if not defined, use `-`
- Title: identifier + issue title
- Labels: if none exist, use `-`
- URL: `[link](url)` (last column)

### 4. Summary

At the end, show a summary table with the found statuses:

## Summary

| Team      | Total  | In Progress | In Review | Detailing | Planned | Idea   |
| --------- | ------ | ----------- | --------- | --------- | ------- | ------ |
| AAA       | X      | Y           | -         | Z         | W       | V      |
| BBB       | X      | Y           | -         | Z         | W       | V      |
| **Total** | **XX** | **YY**      | **-**     | **ZZ**    | **WW**  | **VV** |

**Note:** Include only status columns that exist in the returned issues.

## Usage Examples

- `/linear-my-issues` → list active issues for the logged-in user (detects email automatically)
- `/linear-my-issues john@gabriel.com.br` → John's active issues
- `/linear-my-issues Maria` → Maria's active issues
