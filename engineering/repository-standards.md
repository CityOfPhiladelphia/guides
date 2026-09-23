# Repository Standards

> **Status:** ⚪ Draft
> **Last reviewed:** YYYY-MM-DD

## Purpose

## Scope

## The standard

### Repository naming

### Required files

### Settings

### Branch protection
The `main` branch must be protected: no direct pushes, all changes go through a pull request. Importable rulesets are in [`rulesets/`](rulesets/).

| Ruleset | Applies to | What it enforces |
| --- | --- | --- |
| [`default-branch-baseline.json`](rulesets/default-branch-baseline.json) | The default branch of every repository | The branch can't be deleted or force-pushed. Changes must go through a pull request with 1 approval. New commits dismiss earlier approvals, and all review threads must be resolved before merging. |
| [`default-branch-strict.json`](rulesets/default-branch-strict.json) | The default branch of higher-risk repositories | Everything in baseline, plus 2 approvals, code owner review, approval from someone other than whoever pushed last, linear history (no merge commits), and signed commits. |
| [`release-tags.json`](rulesets/release-tags.json) | Tags matching `v*` | Release tags can't be deleted, moved, or force-updated. |

None of the rulesets allow anyone to bypass them, and none include required status checks, because check names differ in every repository. Teams should add their CI checks after importing.

### Branch naming
Branch naming conventions will be defined in the [Git](git.md) guide.

## How to apply it

## Exceptions
> **TODO:** The baseline ruleset should be applied to all repositories. Any exception must be requested. Define who approves exceptions and how the request is made.

## References
