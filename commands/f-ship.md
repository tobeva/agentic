---
allowed-tools: Bash(git *), Bash(gh pr create *), Bash(cd web && npm run build)
---

# Ship Feature

Commit pending changes and open a PR into main.

## Usage
`/f-ship <description>`

## Steps
1. Run TypeScript build check: `cd web && npm run build`
   - This runs `tsc -b && vite build` which catches type errors that would fail during deployment
   - If this fails, fix the errors before proceeding
2. Stage all changes
3. Commit with the provided description
4. Push the current branch to origin
5. Create a PR into main with the description as the title

# Indciate of PR
"Website" - the main app/website/game
"Backend" - server for main app
"Backlog" - the admin web app or its backend


The commit message and PR title will be: `$ARGUMENTS`
