---
allowed-tools: Bash(git *)
---

# Feature Stat

Show the current status of this feature branch: what's been committed and what's
still local. Useful when returning to a session after some time away.

## Usage
`/f-stat`

## Steps

Run these commands and summarize the results:

```bash
# Show current branch
git branch --show-current

# Show commits on this branch not in main
git log main..HEAD --oneline

# Show uncommitted changes summary
git status --short

# Show file change stats vs main
git diff main --stat
```

## Output Format

Provide a clear summary with these sections:

1. **Branch**: Current branch name
2. **Commits on this branch**: List commits not yet in main (if any)
3. **Uncommitted changes**: Files modified/added/deleted locally (if any)
4. **Summary**: A brief 1-2 sentence description of what this branch is about based on the commits and changes
