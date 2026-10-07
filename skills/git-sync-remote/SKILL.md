---
name: git-sync-remote
description: Fetch and fast-forward the default branch or specified starting branch before beginning work or creating a branch. Use for /git-sync-remote or requests to start from current remote commits.
---

# Git sync remote

Sync the branch that new work will start from before creating a branch or changing files.

1. Inspect the repository, worktree status, current branch, and remotes. Use the starting branch specified by the user or established by the current task. Otherwise resolve the remote's default branch from its HEAD; do not assume `main` or `master`. Prefer the branch's configured upstream remote, then `origin`, then the sole remote. Ask only if the target remains ambiguous.
2. Fetch the selected remote. Resolve its default branch from fresh remote information when needed. If fetching fails or the remote branch is missing, stop and report the problem; cached refs do not establish freshness.
3. Update the local starting branch with a fast-forward only. When it is checked out, use `git merge --ff-only <remote-tracking-ref>` after fetching, or an explicit `git pull --ff-only <remote> <branch>`. If it is checked out in another worktree, perform the update there. If it is not checked out anywhere, fast-forward its ref without switching the user's checkout. A missing local branch may be created from the fetched remote branch.
4. Preserve uncommitted work and local commits. Never reset, force-update, automatically stash, rebase, or create a merge commit. If local changes obstruct the update or the histories diverge, stop and explain what needs resolution.
5. Verify that the fetched remote tip is an ancestor of the local starting branch using `git merge-base --is-ancestor <remote-tracking-ref> <local-ref>`. Report the branch, remote, resulting commit, and whether it advanced, was already current, or contains additional local commits. Only then continue the original task from that branch.

If the task explicitly starts from a fixed commit or tag, preserve that choice and explain that it is pinned rather than moving it to the remote branch tip. Running this skill authorizes fetching and a safe local fast-forward; it does not authorize pushing.
