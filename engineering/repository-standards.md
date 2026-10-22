# Repository Standards

> **Status:** 🟢 Adopted
> **Last reviewed:** 2026-09-22

## Repository naming
> **TODO:** Repos are named all over the place. We have no way of tying them back to a product. Ex: contracts-hub is used in phila.gov, but is a standalone repo.

## Required files
- Every repository **must** have a `README.md` based on the [README template](readme-templates/README.md). See [Documentation](documentation.md#technical-documentation).
- Every repository **must** have a `.github/CODEOWNERS` file that lists GitHub teams (such as `@CityOfPhiladelphia/<team-name>`), not individual users, so reviews and notifications reach whoever is on the team now. It's the single source of truth for who owns the repository; the README links to it.
- Every repository **must** have a PR template at `.github/pull_request_template.md`. See [PR Standards](pr-standards.md#pr-template).

## Settings
Branches **should** be deleted from the remote after their PR is merged, so repositories don't fill up with stale branches. Turn on **Automatically delete head branches** (Settings → General → Pull Requests) to do this for you. Protected branches such as `staging` aren't affected, because the rulesets block their deletion.

## Branch protection
The `main` and `staging` branches **must** be protected: no direct pushes, all changes go through a pull request. See [Git](git.md#branches) for how branches are used. Importable rulesets are in [`rulesets/`](rulesets/).

| Ruleset | Applies to | What it enforces |
| --- | --- | --- |
| [`default-branch-baseline.json`](rulesets/default-branch-baseline.json) | `main` (the default branch) and `staging` in every repository | The branch can't be deleted or force-pushed. Changes must go through a pull request with 1 approval. New commits dismiss earlier approvals. |
| [`default-branch-strict.json`](rulesets/default-branch-strict.json) | `main` and `staging` in higher-risk repositories | Everything in baseline, plus 2 approvals, code owner review, approval from someone other than whoever pushed last, all review threads resolved, and signed commits. |
| [`release-tags.json`](rulesets/release-tags.json) | Tags matching `v*` | Release tags can't be deleted, moved, or force-updated. |

None of the rulesets allow anyone to bypass them, and none include required status checks, because check names differ in every repository. Teams **should** add their CI checks after importing.

Every repository **must** apply at least the baseline ruleset. Exceptions follow the [exceptions process](../CONTRIBUTING.md#exceptions).

## Branch naming
Branch naming conventions are defined in the [Git](git.md#branch-naming) guide.
