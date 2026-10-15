# PR Standards

> **Status:** ⚪ Draft
> **Last reviewed:** 2026-10-08

## Ready for review
A PR is ready for review only when it meets every item below. Authors **must not** request review until it does. Every item is a **must** unless it says otherwise.

- It links to the Wrike ticket for the work.
- Every section of the [PR template](#pr-template) is filled in. Sections that don't apply are deleted.
- The description is written by the author. AI **may** help with the code, but a person **must** write the PR description and own the PR.
- For UI changes, it includes screenshots of the change and a link to the relevant Figma designs.
- Documentation is updated. See [Documentation](documentation.md).
- The author has run every script or command included in the PR or its documentation.
- The code meets the [Code Quality](code-quality.md) standards, including unit tests for new work. Until CI/CD checks are in place, PRs **should** also mention test coverage.

PRs from `staging` to `main` are the exception: they bundle many changes, so they don't link a single Wrike ticket. Each change they include is already traceable through its own merged PR.

## PR size
Small PRs respect the reviewer's attention and workload. There's no fixed limit on files or lines, but:
- Each PR **should** be atomic: tied to the smallest unit of business logic, a single Wrike ticket.
- A reviewer **should** be able to go through the PR in less than 15 minutes, short enough to walk through in a daily scrum.
- PRs **may** be larger at the start of a project, but a larger PR **must** include more documentation to help the reviewer.

## PR template
Every repository **must** have a PR template. See [Repository Standards](repository-standards.md#required-files).

A barebones template is in [`pr-templates/pull_request_template.md`](pr-templates/pull_request_template.md). It has a section for each item above: a Wrike ticket link, what changed and why, testing, and screenshots for UI changes. To use it, copy it to `.github/pull_request_template.md` in your repository.

Teams that want a more detailed template **may** extend it. The [CFPB template](https://github.com/cfpb/development/blob/main/.github/PULL_REQUEST_TEMPLATE.md) is a good example.
