# AI Project Governance Starter

This repository provides a starting point for projects that need strong
governance for AI‐assisted development. It contains templates for
documentation, versioning, and agent guidance that you can copy into a
new application.

## Contents

* `README.md` – this overview.
* `CHANGELOG.md` – a **Keep a Changelog** formatted file with an Unreleased section.
* `.env.example` – a sample environment file listing required variables.
* `.editorconfig` – consistent formatting rules.
* `.gitignore` – ignores build artefacts, dependencies, and secrets.
* `.github/` – GitHub-specific configuration including a pull request
  template and Copilot instructions.
* `docs/` – core documentation:
  * `AGENT_HANDBOOK.md` – the single source of truth for agent
    behaviour, architecture rules, and general policies.
  * `AGENT_ROLES.md` – defines each agent’s responsibilities.
  * `WORKFLOW.md` – outlines the phased build process with gates and
    hand‑offs between agents.
  * `VERSIONING.md` – describes the semantic versioning policy.
  * `RELEASE_PROCESS.md` – describes the steps for performing a
    release and updating documentation.

The other root files (e.g. `CLAUDE.md`, `CODEX.md`, `BLACKBOX.md`,
`.cursor/rules.md`, `.windsurfrules`) provide tool‑specific adapters
that reference the canonical agent handbook and set boundaries for each
assistant.

> **Note:** To use these templates in a new project, copy this
> directory into the root of your repository and customise the
> contents to reflect your stack (React, Laravel, WordPress, etc.).

