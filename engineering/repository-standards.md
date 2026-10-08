# Repository Standards

> **Status:** ⚪ Draft
> **Last reviewed:** 2026-09-23

## Repository naming
> **TODO:** Repos are named all over the place. We have no way of tying them back to a product. Ex: contracts-hub is used in phila.gov, but is a standalone repo.

## Required files
- Every repository **must** have a PR template at `.github/pull_request_template.md`. See [PR Standards](pr-standards.md#pr-template).

## Settings
> **TODO:** Repository cleanup: branches should be deleted from the remote after their PR is merged. Consider turning on **Automatically delete head branches** (Settings → General → Pull Requests).

## Branch protection
The `main` and `staging` branches **must** be protected: no direct pushes, all changes go through a pull request. See [Git](git.md#branches) for how branches are used. Importable rulesets are in [`rulesets/`](rulesets/).

| Ruleset | Applies to | What it enforces |
| --- | --- | --- |
| [`default-branch-baseline.json`](rulesets/default-branch-baseline.json) | `main` (the default branch) and `staging` in every repository | The branch can't be deleted or force-pushed. Changes must go through a pull request with 1 approval. New commits dismiss earlier approvals, and all review threads must be resolved before merging. |
| [`default-branch-strict.json`](rulesets/default-branch-strict.json) | `main` and `staging` in higher-risk repositories | Everything in baseline, plus 2 approvals, code owner review, approval from someone other than whoever pushed last, linear history (no merge commits), and signed commits. |
| [`release-tags.json`](rulesets/release-tags.json) | Tags matching `v*` | Release tags can't be deleted, moved, or force-updated. |

None of the rulesets allow anyone to bypass them, and none include required status checks, because check names differ in every repository. Teams **should** add their CI checks after importing.

> **TODO:** The baseline ruleset should be applied to all repositories. Any exception must be requested. Define who approves exceptions and how the request is made.

## Branch naming
Branch naming conventions are defined in the [Git](git.md#branch-naming) guide.
