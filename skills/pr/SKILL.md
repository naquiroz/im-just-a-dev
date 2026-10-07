---
name: pr
description: Complete requested work and open or reuse a pull request for its branch. Use for /pr new or requests to publish a branch as a pull request.
---

# PR

## New

1. Use the requested or current work branch and checkout. Honor an explicit PR base; otherwise use the carried remote base or target repository's default. A pinned commit/tag needs a branch target. Resolve target repository and push remote separately for forks.
2. On the starting/base branch, use [branch](../branch/SKILL.md) first. Complete the requested feature and relevant checks before publishing.
3. Review the diff against the base; stop if empty. Commit only requested work. Push explicitly to the head branch without force, never to a base-tracking upstream.
4. Find an open PR for this repository and head. Reuse a matching base; stop on a mismatched base. Otherwise create. Describe the final changes and checks in its title and body.
5. Verify head and base. Return the URL and check results. Attach it to the current chat when supported.
