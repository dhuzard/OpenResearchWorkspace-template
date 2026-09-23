# OpenResearchWorkspace Template

**Minimal GitHub template for creating a researcher-owned OpenResearchWorkspace (ORW) project.**

> [!IMPORTANT]
> **This repository is the GitHub template distribution, not the ORW software-development repository.**
> The canonical ORW specification, schemas, CLI, browser generator, validation logic, FAIR/RO-Crate tooling, tests, and development documentation live in [`dhuzard/OpenResearchWorkspace`](https://github.com/dhuzard/OpenResearchWorkspace).

## Which repository do I need?

| If you want to… | Use |
| --- | --- |
| Create a new research project on GitHub | **This repository: `OpenResearchWorkspace-template`** |
| Understand or implement the ORW specification | [`OpenResearchWorkspace`](https://github.com/dhuzard/OpenResearchWorkspace) |
| Develop the ORW CLI, browser generator, validator, FAIR/RO-Crate support, agents, or MCP integrations | [`OpenResearchWorkspace`](https://github.com/dhuzard/OpenResearchWorkspace) |
| Contribute to the minimal GitHub researcher workflow | **This repository** |

## What this repository is

This repository is a **thin GitHub-specific adapter** for ORW. Its purpose is to let a researcher create a clean ORW-compatible workspace using GitHub's **Use this template** workflow without inheriting ORW's development source tree.

The intended flow is:

```text
OpenResearchWorkspace
canonical ORW specification + tooling
          │
          │ defines and validates
          ▼
OpenResearchWorkspace-template
minimal GitHub distribution
          │
          │ Use this template
          ▼
your-research-project
independent ORW workspace
```

A research project created from this template becomes **your independent workspace**. It is not a fork of the ORW development project and does not need to continuously merge changes from this template.

## Source-of-truth rule

The canonical ORW scientific model does **not** live here.

This repository must not independently redefine:

- Investigation → Study → Assay semantics;
- canonical metadata schemas;
- validation rules;
- FAIR or RO-Crate generation behavior;
- workspace mutation semantics;
- agent or MCP policy.

Those belong in [`OpenResearchWorkspace`](https://github.com/dhuzard/OpenResearchWorkspace). Template changes should be generated from, pinned to, or tested against a specific ORW version so that this repository cannot silently drift into a second implementation.

## What should live here

The final template should remain intentionally small and researcher-facing, approximately:

```text
my-research-project/
├── README.md
├── studies/
│   └── study-01/
│       ├── data/
│       ├── assays/
│       ├── analysis/
│       ├── results/
│       └── protocols/
├── references/
├── project-docs/
├── .research/
└── .github/          # GitHub-specific setup adapter
```

It should contain only the workspace scaffold and the minimum GitHub-specific initialization machinery required for a researcher.

It should **not** contain ORW development internals such as `src/`, the browser application, the full test suite, package/release machinery, or a separate copy of the canonical specification.

## Status

This repository has just been separated from the main ORW development repository. The minimal template scaffold and GitHub initialization workflow still need to be migrated here and connected to the canonical ORW generation/validation contract.

For the current ORW implementation and documentation, see [`dhuzard/OpenResearchWorkspace`](https://github.com/dhuzard/OpenResearchWorkspace).
