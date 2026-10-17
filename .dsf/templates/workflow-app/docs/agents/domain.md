# Domain docs

How the engineering skills read this repo's domain documentation.

## Before exploring, read these

- `GLOSSARY.md` at the repo root.
- `docs/architecture/adr/`: ADRs for the area you work in. `docs/architecture/modules.json` says which module owns what.

If a file does not exist yet, proceed silently; `/domain-modeling` creates it when a term or decision is resolved.

## Use the glossary's vocabulary

Name domain concepts in issues, tests and code exactly as `GLOSSARY.md` defines them.

## Flag ADR conflicts

If your output contradicts an accepted ADR, say so explicitly. ADRs are written from `.dsf/templates/adr.md`, and an accepted ADR is superseded by a new one, never edited.
