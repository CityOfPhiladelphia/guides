# Contributing

These guides are meant to grow as teams across the City and OIT build out their practices. This page explains how to add to them so the repo stays easy to navigate.

## Adding a new guide
1. Pick the section it belongs to (`engineering/`, `product-agile/`, …). If none fit, create a new section folder with its own `README.md` index, add the section to the root [README.md](README.md), and propose it in your PR.
2. Copy [templates/standard-template.md](templates/standard-template.md) into that section as a kebab-case file named after the topic, for example `engineering/secrets-management.md`.
3. Fill it in. Start with a short intro under the status line, then give each topic its own `##` heading. Add a `## References` section only if you have links.
4. Put any importable files (JSON, YAML, templates) in a subfolder of the section named for what they are, for example `engineering/rulesets/`. Link to them from your guide and explain how to use them there.
5. Add a row for your guide to the table in the section's `README.md`. The root [README.md](README.md) lists sections only, so it only needs updating when you add a new section.
6. Open a pull request.

## Conventions
- **Folder and file names:** lowercase kebab-case (`pr-standards.md`, `default-branch-baseline.json`).
- **One file per guide:** guides are named for their topic, not `README.md`, so they're easy to find in search and in editor tabs. `README.md` is used only for section indexes.
- **Splitting a large guide:** if a guide outgrows one file, turn it into a folder with the same name (`engineering/git/`) holding kebab-case subtopic files plus a `README.md` index, and update the links that pointed to the old file.
- **Status:** every guide starts with a status line (⚪ Draft, 🟡 Proposed, or 🟢 Adopted). New guides start as Draft or Proposed. A guide moves to Adopted only after review by the maintainers.
- **Links:** use relative links between guides so they work in forks and clones.
- **Must, should, may:** write rules with these words in bold. **Must** is required, **should** is expected unless there's a documented reason not to, and **may** is optional.
- **Open questions:** mark them as `> **TODO:**` blockquotes, in the section they belong to.
- **Configs:** JSON files must be valid and importable as-is. If a value has to be customized per repo, say so in the guide rather than leaving placeholders that break the import.
- **Keep it practical:** say what to do first and why second. Link out to external docs instead of copying them.

## Changing an existing guide
Small fixes (typos, broken links, clarifications) can go straight to a PR. Changes to what an Adopted standard requires should explain the reasoning in the PR description so affected teams can weigh in.

## Exceptions
> **TODO:** Define how a team requests an exception to a standard, and who approves it. Guides only need their own exceptions section if they differ from this process.
