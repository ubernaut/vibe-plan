# Planning guide

This directory holds the durable context needed to understand and continue the
project. Keep it useful and small: record information only when it will affect
future work or prevent a decision from being repeated.

## What to read

For every task, read:

1. `plan.md` for scope and intended outcomes.
2. `todo/priority.md` for the current order of work.
3. The specific task file, when one exists.

Read relevant files from `workflow/`, `arch/`, `test/`, `refs/`, and
`log/log-summary.md` as needed. Do not load `log/log-detail.md` by default. The
LLM should decide when the current task may benefit from prior attempts,
failures, pivots, or unresolved work and scan the log then. Prefer targeted
searches to reading the entire file. This reading rule does not make detailed
logging optional.

## What belongs where

- `plan.md`: user-owned scope, goals, non-goals, success criteria, and
  high-level direction. An LLM may update it only with explicit permission.
- `todo/priority.md`: a short, ordered list of the next actionable tasks.
- `todo/`: one file for work that spans multiple steps or sessions, requires
  meaningful decisions, or needs durable acceptance criteria. Handle small,
  obvious changes directly without creating a task file.
- `todo/done/`: completed task files worth retaining.
- `todo/hiatus/`: paused task files that may be resumed.
- `arch/`: cross-cutting architecture, stack choices, and decisions that affect
  more than one task. Do not document implementation details already obvious
  from the code. Embed simple Mermaid diagrams in the relevant document; keep
  larger or reusable diagram sources in `arch/diagrams/`.
- `test/`: the shared test strategy and project-wide completion expectations.
  Task-specific acceptance checks belong in the task file.
- `workflow/`: lightweight defaults for the development loop and version
  control. Keep them practical; add process only when it prevents recurring
  mistakes or coordination problems.
- `log/log-summary.md`: concise durable progress, decisions, and pivots.
- `log/log-detail.md`: the complete prompt and development record, including
  responses, strategies, attempts, failures, and pivots. Keep it updated, but
  scan it only when the LLM judges that its history may inform the current work.
- `refs/`: reference material that is actually used; link each reference from
  the plan or task that needs it. Replace `refs/_example.md` with the first real
  reference or copy its minimal format when useful.

Use `todo/_template.md` when a task file is warranted. Delete unused template
sections rather than filling them with boilerplate.

## Current and target state

When documentation describes a desired state that differs from the repository,
add brief `Current state` and `Target state` sections to the relevant plan,
architecture, or task file. Remove the distinction once the target is reached.
Do not maintain a separate drift register.

## Maintenance

Update planning files in the same change that makes them inaccurate. Keep the
priority list short. When work finishes or pauses, move its task file and remove
it from the active queue. Delete obsolete references. Keep the detailed log as
history; summarize its durable outcomes in the summary log.
