# Vibe Plan

Vibe Plan is a lightweight, tool-agnostic workspace for planning and tracking a
software project with AI coding assistants. It keeps product direction,
architecture, tasks, tests, references, and development history in predictable
locations so a person or assistant can recover the project's context before
making changes.

This repository currently contains the planning framework only. It does not yet
define a product, application stack, implementation, or runnable test suite.

## Repository layout

```text
plan/
├── plan.md                 # User-owned scope, goals, and high-level plan
├── README.md               # Instructions for maintaining the planning files
├── arch/
│   ├── best-practices.md   # Cross-cutting engineering principles
│   └── stack.md            # Preferred application stack
├── todo/
│   ├── priority.md         # Ordered queue of open work
│   ├── done/               # Completed task files
│   └── hiatus/             # Paused task files
├── test/
│   └── test.md             # Test strategy and test plan
├── log/
│   ├── log-summary.md      # Concise narrative project history
│   └── log-detail.md       # Detailed prompts, decisions, attempts, and results
└── refs/                   # External references, links, PDFs, and source material
```

`AGENTS.md` contains repository instructions for compatible coding assistants.
`CLAUDE.md` points to the same instructions for tools that use that filename.

## Working agreement

1. Read every file under `plan/` before planning or implementation.
2. Keep the project's scope, goals, non-goals, success criteria, and high-level
   plan in `plan/plan.md`. This file is user-owned; an assistant must have
   explicit permission before changing it.
3. Record each unit of work in its own file under `plan/todo/` and list active
   work in `plan/todo/priority.md`.
4. Move completed task files to `plan/todo/done/`; move paused work to
   `plan/todo/hiatus/`.
5. Keep architecture, stack, and testing documents aligned with the actual
   implementation. Call out differences between the documented target and the
   current state.
6. Capture important progress and pivots in `plan/log/log-summary.md`. Use
   `plan/log/log-detail.md` for enough detail to avoid repeating failed work.
7. Store supporting material in `plan/refs/` and link it from the plan or task
   that depends on it.

The engineering principles in `plan/arch/best-practices.md` favor separation of
concerns, clean interfaces, supported and well-established dependencies,
consistent patterns, and hardware-aware performance choices.

## Starting a project

Populate the planning framework in this order:

1. Define the problem, users, scope, non-goals, and success criteria in
   `plan/plan.md`.
2. Record the target architecture and dependency choices under `plan/arch/`.
3. Break the plan into independently verifiable task files under `plan/todo/`.
4. Order the active tasks in `plan/todo/priority.md`.
5. Define test levels, environments, acceptance criteria, and release gates in
   `plan/test/test.md`.
6. Begin the summary and detailed logs as implementation work starts.
