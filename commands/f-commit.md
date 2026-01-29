---
allowed-tools: Bash(git *)
---

# Feature Commit

Commit current changes to the current branch with a meaningful commit message.

## Usage
`/f-commit`

## Steps

1. Check current branch and status:
   ```bash
   git branch --show-current
   git status --short
   git diff --staged --stat
   git diff --stat
   ```

2. If there are no changes, say "Nothing to commit" and stop.

3. Stage all changes:
   ```bash
   git add -A
   ```

4. Review the staged changes to understand what's being committed:
   ```bash
   git diff --staged
   ```

5. Generate a meaningful commit message based on the changes:
   - Summarize the nature of the changes (new feature, bug fix, refactor, etc.)
   - Keep the first line under 50 characters if possible
   - Focus on the "why" not the "what"

6. Commit with the generated message:
   ```bash
   git commit -m "$(cat <<'EOF'
   <commit message here>

   Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com>
   EOF
   )"
   ```

7. Confirm the commit:
   ```bash
   git log -1 --oneline
   ```

## Output Format

Report:
- Branch: `<branch-name>`
- Committed: `<short-hash>` "<commit message>"
- Files changed: N files (+X/-Y lines)
