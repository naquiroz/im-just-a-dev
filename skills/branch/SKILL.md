---
name: branch
description: Create a work branch from a chosen starting point. Use for /branch create, /branch create new, or requests to start work on a new branch.
---

# Branch

## Create

1. Honor an explicit base or reuse the preceding `/git` base and commit. Use [git](../git/SKILL.md) if absent or a moving base needs synchronization. Preserve pinned commits and tags.
2. Use the requested name or `codex/<task>`. "Create new" names the operation. Reuse this task's branch; for other collisions choose a fresh name or ask if the exact name is required.
3. Create and check out from the resolved commit. Preserve related edits; use a worktree for unrelated work. Never replace existing branches or discard edits.
4. Verify the base is an ancestor of the head. Pass checkout path, head, and PR base to `/pr`.
