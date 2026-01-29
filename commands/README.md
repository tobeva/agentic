# Feature Branch Commands

Git workflow commands for feature branch development.

## Workflow

### On Feature Branch

1. **`/f-new [name]`** - Create a new feature branch off latest main
   - With name: `feature/<name>`
   - Without: `feature/wip-<timestamp>`

2. **`/f-name <name>`** *(optional)* - Rename current branch to `feature/<name>`

3. **`/f-commit`** - Stage all changes and commit with auto-generated message

4. **`/f-stat`** - Show branch status: commits ahead of main, uncommitted changes

5. **`/f-ship <description>`** - Run build check, commit, push, and create PR

### On Main Branch

6. **`/f-merge`** - Merge all open PRs into main, report conflicts
