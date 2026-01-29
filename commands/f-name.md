---
allowed-tools: Bash(git branch*)
---

# Name Feature Branch

Rename the current feature branch.

## Usage
`/f-name <new-name>`

## Steps
1. Rename current branch to `feature/$ARGUMENTS`

Run this command:
```bash
git branch -m feature/$ARGUMENTS
```
