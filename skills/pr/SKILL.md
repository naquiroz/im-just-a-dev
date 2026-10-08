---
name: pr
description: Complete requested work and open or reuse a pull request for its branch. Use for /pr new or requests to publish a branch as a pull request.
---

# PR

## New

Publish the requested or current work branch from its selected checkout. PR base precedence is explicit branch, carried remote base, then target repository default. A pinned commit/tag requires a branch target. Resolve target repository and push remote independently for forks.

Use [branch](../branch/SKILL.md) when the checkout is still on the starting/base branch. Complete the requested feature and relevant checks before publishing. Review the base-to-head diff; an empty diff produces no PR. Commit only requested work. Push explicitly to the head branch without force, never to a base-tracking upstream.

Reuse an open PR for this repository and head when its base matches; a mismatched base stops publication. Otherwise create the PR. Its title and body describe final changes and check results. Return the URL with verified head, base, and check results. Attach it to the current chat when supported.
