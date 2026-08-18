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
│   ├── _template.md        # Minimal template for nontrivial tasks
│   ├── done/               # Completed task files
│   └── hiatus/             # Paused task files
├── test/
│   └── test.md             # Test strategy and test plan
├── log/
│   ├── log-summary.md      # Concise durable progress and decisions
│   └── log-detail.md       # Complete prompt and development record
└── refs/                   # External references, links, PDFs, and source material
```

`AGENTS.md` contains repository instructions for compatible coding assistants.
`CLAUDE.md` points to the same instructions for tools that use that filename.

## Working agreement

1. Read `plan/README.md`, `plan/plan.md`, and `plan/todo/priority.md` first.
   Load other planning files only when they are relevant to the current work.
2. Keep the project's scope, goals, non-goals, success criteria, and high-level
   plan in `plan/plan.md`. This file is user-owned; an assistant must have
   explicit permission before changing it.
3. Create a task file only for work that spans multiple steps or sessions,
   requires meaningful decisions, or needs durable acceptance criteria. List
   active task files in `plan/todo/priority.md`.
4. Move completed task files to `plan/todo/done/`; move paused work to
   `plan/todo/hiatus/`.
5. Keep architecture, stack, and testing documents aligned with the actual
   implementation. Call out differences between the documented target and the
   current state.
6. Capture durable progress and pivots in `plan/log/log-summary.md`, and keep
   the prompt and development record in `plan/log/log-detail.md`. Maintaining
   the detailed log is expected; the LLM decides when prior-work context makes
   a targeted scan useful.
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
3. Create independently verifiable task files for nontrivial work under
   `plan/todo/`.
4. Order the active tasks in `plan/todo/priority.md`.
5. Define test levels, environments, acceptance criteria, and release gates in
   `plan/test/test.md`.
6. Maintain both logs as implementation progresses. Do not load the detailed
   log routinely; scan it when prior attempts may inform the current work.
