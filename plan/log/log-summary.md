# Development summary

Record concise, durable progress, decisions, and pivots that will help someone
resume the project. Do not duplicate task files, commit history, or routine chat.

Add dated entries in reverse chronological order when there is something worth
preserving.

## 2026-08-18

- Added lightweight development-loop and trunk-based version-control guidance
  under `plan/workflow/`.
- Added a pre-merge gate that deploys the pull-request revision to test
  infrastructure and runs integrated tests before merging to `main`.
- Defined the full branch loop: local development, upstream rebase and smoke
  test, PR deployment and integration tests, then merge and production deploy;
  failures return to branch development.
- Added a minimal reference example so Git preserves `plan/refs/`.
- Added a root README explaining the planning framework.
- Made routine context loading progressive instead of requiring every plan file.
- Added minimal plan and task templates plus a threshold for task-file creation.
- Defined lightweight current-versus-target and pruning conventions.
- Kept detailed development logging continuous while making scans selective and
  LLM-directed rather than part of baseline context loading.
- Added `arch/diagrams/` for standalone architecture diagram sources while
  keeping simple diagrams inline and diagram creation optional.
