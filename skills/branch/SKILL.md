---
name: branch
description: Create a work branch from a chosen starting point. Use for /branch create, /branch create new, or requests to start work on a new branch.
---

# Branch

## Create

Create and check out the work branch from the explicit base or preceding `/git` base commit. Use [git](../git/SKILL.md) to resolve an absent base or refresh a moving base when needed. Pinned commits/tags stay fixed.

By default use provided branch name; otherwise use `<harness>/<task>`. "Create new" selects the capability. Reuse this task's existing branch. Other name collisions require a fresh name or clarification when the exact name is required. Preserve related edits in the selected checkout; isolate unrelated work in a worktree. Never replace existing branches or discard edits.

The resolved base commit must be an ancestor of the head. Pass checkout path, head branch, and retained PR base to `/pr`.
