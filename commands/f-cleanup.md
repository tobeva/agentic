# Feature Cleanup

Clean up code for an in-progress feature using Brain-Oriented Programming principles.

## Usage
`/f-cleanup [file-or-directory]`

If no argument provided, analyze recently modified files on the current branch.

## Brain-Oriented Programming Principles

The brain can only hold 5-9 things in working memory. Code that exceeds this
limit becomes hard to reason about. Apply these rules:

### 1. Limit Object Attributes to 7 or Fewer
- Count attributes on classes/objects touched by this feature
- Objects with 8+ attributes are a code smell requiring immediate action
- Methods don't count—only stateful attributes matter

### 2. Use Chunking via Sub-objects
When an object approaches the limit, group related attributes:
- Replace `start_ns` and `end_ns` with a `Span` object
- Replace `x`, `y`, `width`, `height` with a `Rect` object
- This creates reusable components and reduces cognitive load

### 3. Push Functionality Down
- Move methods that only use sub-object data into the sub-object
- Example: If `get_duration_ns()` only uses `span.start_ns` and `span.end_ns`, move it to `Span`

### 4. Organize as Natural Trees
- Allow objects to grow into branching hierarchies
- Deep trees with small nodes are easier to understand than flat structures with large nodes

## Steps

1. Identify files changed in current feature branch:
   ```bash
   git diff --name-only origin/main...HEAD
   ```

2. For each class/object in changed files:
   - Count attributes (ignore methods)
   - Flag any with 8+ attributes
   - Look for groups of 2-3 related attributes that could become sub-objects

3. Report findings with specific refactoring suggestions

4. If user approves, perform the refactoring

## Output Format

For each file analyzed, report:
- Classes/objects and their attribute counts
- Specific violations of the 7-attribute rule
- Suggested groupings for sub-objects
- Any methods that should move to sub-objects
