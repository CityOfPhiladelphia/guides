# Guides | City of Philadelphia - Office of Innovation and Technology
The goal of this repository is to act as a central place for engineering practices at the City of Philadelphia - Office of Innovation and Technology (OIT).

Confluence remains the main home for documentation. This repository holds technical GitHub and engineering policies, and is linked from Confluence.

Guides are grouped into section folders (such as `engineering/`), and each guide is a single kebab-case Markdown file (such as `engineering/code-review.md`). Each section's `README.md` lists its guides. Importable configurations (GitHub rulesets, templates, and so on) live in a subfolder of the section that uses them.

Want to add or change a standard? See [CONTRIBUTING.md](CONTRIBUTING.md).

## Status legend
Every guide has a status at the top so readers know how much weight to give it.

| Status | Meaning |
| --- | --- |
| 🟢 Adopted | Agreed upon; teams are expected to follow it. |
| 🟡 Proposed | Written and open for feedback; not yet required. |
| ⚪ Draft | Placeholder or work in progress. |

Currently, the following sections have been worked on or are under active development:

## [Engineering](engineering/)
Our goal is to develop secure and dependable software for the City of Philadelphia.

## [Product / Agile](product-agile/)
Engineering teams can employ tools such as agile software development in order to build the right products.

## Inspiration
These guides draw on the work of other public-sector technology teams:

- [18F Guides](https://github.com/18F/guides/tree/main) (U.S. General Services Administration)
- [GOV.UK Service Manual](https://www.gov.uk/service-manual) & [Developer Docs](https://docs.publishing.service.gov.uk/)(UK Government Digital Service)

## Repository layout
```
.
├── README.md                 # You are here: index of all guides
├── CONTRIBUTING.md           # How to propose or update a standard
├── templates/                # Starting points for new guides
├── engineering/
│   ├── README.md             # Section index
│   ├── repository-standards.md
│   ├── git.md
│   ├── code-quality.md
│   ├── pr-standards.md
│   ├── code-review.md
│   ├── documentation.md
│   ├── accessibility.md
│   ├── rulesets/             # Importable GitHub ruleset JSON
│   ├── vscode/               # Shared VS Code extensions and settings
│   ├── prettier/             # Shared Prettier config
│   └── pr-template/          # Barebones PR template
└── product-agile/
    └── README.md             # Section index
```

## Disclaimer

AI tools may have been used to clean up files and help organize this repository. All content is reviewed by City of Philadelphia staff.
