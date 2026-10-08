---
name: git
description: Fetch and fast-forward a starting branch before new work. Use for /git sync remote or requests to pull the latest base commits.
---

# Git

## Sync remote

Sync the explicit or established base. Remote precedence is explicit selection, base upstream, `origin`, then the sole remote. Resolve an unspecified base from live remote HEAD. Use its upstream on that remote or the matching branch; ask if ambiguous.

Freshness requires an explicit upstream fetch and its fetched commit. Fetch failure or a missing remote branch stops sync. Pinned commits/tags stay fixed after a successful remote fetch. Branch bases must contain the fetched commit. Existing containment needs no update; create an absent base from that commit. Updates are fast-forward only. A checked-out base uses `git merge --ff-only --no-autostash <fetched-tip>` in its worktree. An unchecked base uses `git update-ref` with the expected old tip after verifying that tip is an ancestor of the fetched commit.

Preserve local commits and edits. Divergence or obstructing edits stops sync. Sync never stashes, rewrites history, or pushes. Verify containment with `git merge-base --is-ancestor <fetched-tip> <local-base>`. Report base and commit; retain source remote, remote base, local base, and commit for chained operations.
