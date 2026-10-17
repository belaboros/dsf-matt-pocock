# Workflow layer: Matt Pocock skills

Skill pack: [mattpocock/skills](https://github.com/mattpocock/skills) (plugin `mattpocock-skills@mattpocock`). The pack's per-repo configuration is already written in `docs/agents/` (issue tracker = this app's task backend, ADRs in `docs/architecture/adr/`), so do not run `/setup-matt-pocock-skills` unless the human asks; if it runs, it writes its `## Agent skills` block into `CLAUDE.app.md`, never into `CLAUDE.md`.

| Factory step (docs/dsf/workflows.md) | Mode | Skill | Output goes to |
| --- | --- | --- | --- |
| PRD interview | design | `/grill-with-docs` (relentless interview that also writes the glossary and ADRs), then `/to-spec` | `specs/prd.md`, `GLOSSARY.md` |
| UAT interview | design | `dsf-uat-interview` (factory skill); `/grill-me` to stress-test the scenarios | `uat/features/` |
| Architecture | design | `dsf-architect`, using `/codebase-design` (deep modules, seams) and `/domain-modeling` | `docs/architecture/` |
| Plan into tasks | design | `/to-tickets` (tracer-bullet tickets with blocking edges); `/wayfinder` for work bigger than one session | the task backend |
| Build | build | `/implement` (or `/implement-spec`) with `/tdd` | `src/`, tests, `uat/steps/` |
| Bugfix | build | `/diagnosing-bugs`, then `/tdd`; `/triage` for incoming issues | failing test first, then the fix |
| Review | build | `dsf-code-reviewer`; `/code-review` as a second pass on standards and spec | PR comments |
| PR | build | `/pr` for the description | PR |
| Exploration | design | `/research` and `/prototype` on a `spike/` branch | `docs/architecture/proposals/` |
| Architecture maintenance | design | `dsf-arch-maintenance`, with `/improve-codebase-architecture` for deepening options | `docs/architecture/proposals/` |
| Factory | factory | `dsf-factory-improve`; `/retro` after a session to collect lessons; `/writing-for-agents` for skills | `.claude/skills/` |

Where the pack and this factory differ, the factory wins:

- `/to-spec` publishes to the issue tracker by default. Here the spec is a file: write it to `specs/prd.md` (or `specs/features/<feature>.md`) and link it from the task.
- The pack keeps ADRs in `docs/adr/`. Here they live in `docs/architecture/adr/` and use `.dsf/templates/adr.md`.
- Ticket labels: use the factory's `type:*` and `status:*` labels; `docs/agents/triage-labels.md` maps the pack's triage roles onto them.
