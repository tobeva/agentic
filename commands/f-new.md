---
allowed-tools: Bash(git fetch*), Bash(git checkout*)
---

# New Feature Branch

Create a new feature branch off latest main (worktree-safe).

## Usage
`/f-new [branch-name]`

## Steps
1. Fetch latest from origin
2. Create new branch based on origin/main
   - If name provided: `feature/$ARGUMENTS`
   - If no name: `feature/wip-<timestamp>`

Run these commands:
```bash
git fetch origin && git checkout -b feature/${ARGUMENTS:-wip-$(date +%Y%m%d-%H%M%S)} origin/main
```
