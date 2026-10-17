# Issue tracker

This repo's task backend is **{{TASKS_BACKEND}}** (set once in `.dsf.app`). {{TASKS_HINT}}

## When a skill says "publish to the issue tracker"

Create the task in that backend, using the factory's vocabulary: `type` (`feature`, `bug`, `arch-decision`, `dsf`, `research`) and `status` (`todo`, `doing`, `blocked`, `done`, `needs-human`). Every task links its spec section in `specs/` and its UAT scenarios in `uat/features/`. Specs themselves are files in `specs/`, not issues.

## When a skill says "fetch the relevant ticket"

Read it from the same backend; the human normally passes the id or path.

## Blocking edges

Record "blocked by" as the backend allows: `depends_on` in a Markdown task, a dependency in Backlog.md or Beads, or a "Blocked by #n" line in a GitHub issue.
