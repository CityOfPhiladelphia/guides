# Git

> **Status:** ⚪ Draft
> **Last reviewed:** 2026-10-08

## Branches
Every repository **should** have three long-lived branches:

| Branch | Purpose | Protected | How it's updated |
| --- | --- | --- | --- |
| `main` | Production | Yes | Pull requests from `staging` only |
| `staging` | Pre-production | Yes | Pull requests only |
| `dev` | Working branch for testing your work | No | Direct pushes and merges, no PR needed |

- `main` and `staging` **must** be protected so they can only be updated through pull requests. The [rulesets](repository-standards.md#branch-protection) protect both.
- `main` **must** only be updated by pull requests from `staging`.
- `dev` has no contract or expectations. You **may** push or merge to it directly to test your work, without going through a PR.
- `dev` **must not** be merged into `staging` or `main`, because it holds other people's untested work. Changes reach `staging` through a PR from their own branch.

`dev` could be stopgap until we have ephemeral environments: environments that are spun up and torn down automatically for each branch or PR.

## Branch naming
Working branches **must** be named `<type>/<wrike-id>-<short-description>`:
- **Type:** one of the prefixes below.
- **Wrike ID:** the ID of the Wrike ticket for the work.
- **Short description:** two or three words in lowercase kebab-case.

| Prefix | Use it for | Example |
| --- | --- | --- |
| `feat/` | New features or enhancements | `feat/1234567890-permit-search` |
| `bugfix/` | Fixes for bugs found before release | `bugfix/1234567890-login-redirect` |

## Version and release tagging
Releases are typically made from `main` and marked with a tag starting with `v`, such as `v1.4.0`. The [`release-tags`](rulesets/release-tags.json) ruleset protects these tags so they can't be moved or deleted.

> **TODO:** Define the version number format.

## Commit messages
> **TODO:** Define structure for commit messages. Shall we adopt [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)?

## References
- [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)
