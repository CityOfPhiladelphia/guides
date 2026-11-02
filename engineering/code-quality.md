# Code Quality

> **Status:** 🟢 Adopted
> **Last reviewed:** 2026-10-22

## Development setup

### Editor
Most of our engineers use [VS Code](https://code.visualstudio.com/). Shared configs live in [`vscode/`](vscode/):

| File | What it does |
| --- | --- |
| [`extensions.json`](vscode/extensions.json) | Recommended extensions. VS Code prompts anyone who opens the repository to install them. |
| [`settings.json`](vscode/settings.json) | Workspace settings. Formats files on save, with the right formatter for each language. |

Both files are split into commented blocks: **All projects**, **Front end**, **Vue**, **Java**, and **.NET**. To use them:
1. Copy both files into a `.vscode/` folder at the root of your repository.
2. Keep the **All projects** block and the blocks for your stack. For full stack work, keep every block you need.
3. Delete the rest, and make sure the last entry in each list doesn't end with a comma.

### Formatting
JavaScript and TypeScript repositories **should** use [Prettier](https://prettier.io/) so formatting is consistent and never comes up in code review. A shared config is in [`prettier/prettier.config.mjs`](prettier/prettier.config.mjs); copy it to the root of your repository.

> **TODO:** Agree on the Prettier settings. The current config was suggested by a team member and is open for discussion.

## Unit testing

### Coverage
- Net new work **must** be covered by unit tests. Existing code without tests is tech debt, to be covered methodically over time.
- If a repository has no test framework when you contribute or open a PR to it, you **must** work with your team to establish one. You **should** share the decision with the wider engineering organization as needed, so teams can stay consistent.
- Once a repository has test coverage, its unit tests **must** run in the CI/CD pipeline, so tech debt doesn't build up again.

> **TODO:** Define specific test coverage thresholds.

### Writing good tests
Although we have defined coverage thresholds, it is not always the main indicator of quality. A high coverage number doesn't mean the logic is tested.

- Tests **should** exercise the code's logic, not just its lines. Getting this right may take multiple passes over the code.
- Unit tests **should** be easy to run.
- Tests **should** call the public methods of a class (or invoke the public endpoints of a backend, with a mocked database) and assert facts about the effects of that call or sequence of calls.

## Accessibility
Accessibility is part of code quality. See the [Accessibility](accessibility.md) guide.

## Front end styling
> **TODO:** Document the `ux-tokens` repo, which is being set up so Figma styling tokens can be used in code. The tokens will be used in PhilaUI components and **should** be used in any custom front end work.
