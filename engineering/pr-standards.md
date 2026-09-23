# PR Standards

> **Status:** ⚪ Draft
> **Last reviewed:** 2026-09-23

## Purpose

## Scope

## The standard

### What every PR must include
- A link to the Wrike ticket for the work.
- For UI changes: screenshots of the change and a link to the relevant Figma designs.
- A description written by the author. AI may help with the code, but a person must write the PR description and own the PR.
- Updated documentation. See [Documentation](documentation.md).

Before opening a PR, the author must run every script or command included in the PR or its documentation.

> **TODO:** Until CI/CD checks are in place, PRs should mention unit test coverage and include new tests where possible. See [Code Quality](code-quality.md#unit-testing).

### PR template
Every repository must have a PR template. See [Repository Standards](repository-standards.md#required-files).

> **TODO:** An org wide template would be nice. Refer to this [CFPB Template](https://github.com/cfpb/development/blob/main/.github/PULL_REQUEST_TEMPLATE.md) as a good example! Build on the existing PR template work within the team.

### Ready for review
> **TODO:** Define what makes code ready for review, including what documentation must be in place.

### PR size
> **TODO:** PRs should ideally be small and atomic, out of respect for the reviewer's attention and workload. Decide how many files in one PR is too many. PRs can be larger at the start of a project, but they then require more documentation.

## How to apply it

## Exceptions

## References
