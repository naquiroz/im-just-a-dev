---
name: git
description: Fetch and fast-forward a starting branch before new work. Use for /git sync remote or requests to pull the latest base commits.
---

# Git

## Sync remote

1. Use the explicit or established base. Honor an explicit remote; otherwise prefer its upstream remote, `origin`, then the sole remote. Resolve a missing base from live remote HEAD. Use an upstream on that remote or its matching branch; resolve ambiguity. For a pinned commit/tag, fetch successfully and return the unchanged pin.
2. Fetch the upstream explicitly and record its fetched commit. Stop on failure or a missing remote branch.
3. Leave a base containing that commit unchanged. Otherwise create it if absent or fast-forward it. Use `git merge --ff-only --no-autostash <fetched-tip>` in a checked-out base's worktree. For an unchecked base, require ancestry and use `git update-ref` with the expected old tip.
4. Preserve local commits and edits. Stop on divergence or obstructing edits. Synchronization never stashes, rewrites history, or pushes.
5. Verify `git merge-base --is-ancestor <fetched-tip> <local-base>`. Report the base and commit. Carry source remote, remote base, and local base into chained operations.
