---
allowed-tools: Bash(gh *)
---

# Feature Merge

Attempt to merge all open PRs into main. Report any that have conflicts so the
user knows which worktree needs to handle resolution.

## Usage
`/f-merge`

## Steps

1. First, list all open PRs targeting main:
   ```bash
   gh pr list --base main --state open --json number,title,headRefName,mergeable,url
   ```

2. For each PR that is mergeable, merge it:
   ```bash
   gh pr merge <number> --merge
   ```

3. Collect results and report.

## Output Format

For each PR, report:
- ✓ Merged: PR #NNN "Title"
- ✗ Conflict: PR #NNN "Title" (branch: `branch-name`)

At the end, if there were conflicts:
```
PRs with conflicts need manual resolution:
  #158 branch: feature/mobile-one-column (worktree: orson2?)
  #155 branch: fix/image-loading (worktree: orson4?)
```

If no open PRs exist, show the last 5 merged PRs for context:
```bash
gh pr list --base main --state merged --limit 5 --json number,title,headRefName,mergedAt
```

Format as:
```
No open PRs targeting main.

Recently merged:
  #158 "Add mobile responsive layout" (merged 2 days ago)
  #157 "Implement search" (merged 3 days ago)
  ...
```

If all merged successfully, say "All PRs merged successfully!"
