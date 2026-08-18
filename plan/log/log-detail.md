# Detailed development log

Maintain a chronological record of prompts, responses, strategies, attempts,
failures, and pivots throughout development. Logging is not optional.

Reading this file is selective, not routine. The LLM decides when the current
task may overlap prior attempts, failures, pivots, or unresolved work. It should
prefer a targeted search before loading the entire file.

Entries should preserve enough detail to avoid repeating prior work. They may
link to task files, commits, test output, or reference material instead of
duplicating large artifacts.

## 2026-08-18 — Planning framework documentation

### Prompt

Create a project README and identify gaps in the planning framework.

### Response and strategy

Read the complete planning tree, confirmed that the repository is a planning
framework rather than an application, and created a root README describing its
purpose, layout, workflow, and initial gap assessment.

### Prompt

Clarify that scope belongs in `plan.md` and report gaps in chat rather than in
the README.

### Response and strategy

Removed the gap assessment from the README, made `plan.md` ownership of scope
explicit, and reported the gaps conversationally.

### Prompt

Reassess the gaps with ease of use and low ceremony as primary constraints,
then update the plan structure to address them.

### Response and strategy

Kept the existing directory model and introduced progressive context loading,
minimal plan and task templates, a threshold for creating task files, a simple
current-versus-target convention, and pruning guidance. Replaced placeholder
files with concise instructions rather than adding governance directories.

### Correction

The user clarified that reading the detailed log should be opt-in, while
maintaining the log should not be optional. Updated all instructions to preserve
continuous detailed logging while excluding this file from routine context.

The user then clarified that the LLM, rather than the user, should decide when a
detailed-log scan is warranted. Replaced explicit user opt-in with selective,
relevance-based scanning and a preference for targeted searches.

### Prompt

Add a diagrams folder under `plan/arch/` without making diagrams burdensome.

### Response and strategy

Added `plan/arch/diagrams/README.md` and linked the directory from the framework
guides. The convention favors inline Mermaid for simple diagrams, standalone
editable sources for larger or reusable diagrams, and diagrams only when they
clarify the design better than concise prose.

### Prompt

Add a workflow folder with `development.md` describing a typical workflow loop
and `version-control.md` describing trunk-based Git development.

### Response and strategy

Added concise workflow documents covering orientation, outcome definition,
investigation, implementation, verification, documentation reconciliation, and
integration. Defined `main` as a releasable trunk, allowed direct commits for
low-risk solo work when policy permits, and otherwise favored short-lived
branches, frequent integration, focused commits, verification, and no force
pushes to `main`. Linked the folder from the framework and agent instructions.

### Prompt

Add an example reference file so Git tracks the otherwise empty `plan/refs/`
directory.

### Response and strategy

Added `plan/refs/_example.md` with a minimal source, relevance, and rationale
format. Updated the framework guides and logs to identify it as a replaceable
example rather than a required documentation artifact.
