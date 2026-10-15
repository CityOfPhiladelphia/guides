# Documentation

> **Status:** ⚪ Draft
> **Last reviewed:** 2026-10-15

Documentation comes in two kinds:
- **Business and feature documentation** explains *why* something was built, and lives outside the repository.
- **Technical documentation** explains *how* the code works, runs, and deploys, and lives in the repository.

## Business and feature documentation
Business requirements and feature decisions live in Wrike. Code is traced back to them through pull requests: every PR links its Wrike ticket (see [PR Standards](pr-standards.md)), and because we merge with merge commits, every change in the history points back to its PR.

## Technical documentation
The README is the entry point for every repository. Every repository **must** have a README based on the [README template](readme-templates/README.md):

| Section | What it covers |
| --- | --- |
| About | What the repository is for, and where it's used (products, sites, or other repositories). |
| Ownership | A link to the repository's `CODEOWNERS` file, and a shared contact for the team. |
| Standards | A link to these guides, and any exceptions to them, especially branching and CI/CD. Exceptions must be approved or come from legacy decisions. |
| Getting started | Prerequisites, local setup, and an example of how to run the code. |
| Deployment | How code gets to each environment. |
| Testing | How to run the tests. |
| Configuration | Environment variables, and where secrets are stored (never their values). |

- READMEs **must** keep every section, in this order, so anyone can find their way around any repository. If a section doesn't apply, say so in one line.
- How much goes in each section is up to the team. Teams **may** add their own sections after Configuration.
- The Deployment section **must** list every step, especially steps that happen outside CI/CD. For example, if a build uploads a file to S3 that someone then has to link somewhere, that manual step **must** be written down.
- Existing repositories **should** adopt the template the next time their README is updated.

## Writing documentation
- The writer **must** run every script and command included in the documentation.
- Remove all boilerplate (from templates or generated content) before review.
- The writer **must** read through the documentation and confirm it can be understood.

## AI-assisted documentation
The rules above apply to all documentation, including documentation drafted with AI.

> **TODO:** Define AI documentation standards. A series of steps for putting human judgment onto AI-generated documentation.

## Keeping documentation current
- If a repository's documentation is out of date, open a GitHub issue on that repository with the `documentation` label, and notify the team listed in its `CODEOWNERS` file.
- Ownership is recorded in `CODEOWNERS` as a GitHub team, and the README's contact is a shared channel, not an individual, so both stay accurate when people leave.
- When a team changes or is dissolved, its repositories' `CODEOWNERS` files and README contacts **must** be updated as part of the handover.
- If no owner can be reached, contact an engineering lead or manager. They'll assign the repository to the appropriate team, who then update its `CODEOWNERS` file.
