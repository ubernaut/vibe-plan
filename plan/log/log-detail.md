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
