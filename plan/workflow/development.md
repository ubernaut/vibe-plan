# Development workflow

Use the smallest complete loop that moves the project forward without losing
important context.

## The loop

1. **Orient.** Read `plan/README.md`, `plan/plan.md`, and
   `plan/todo/priority.md`, then load only the files relevant to the work.
   Inspect the live repository before relying on documentation. Scan the
   relevant branch detail logs when prior attempts may matter.
2. **Define the outcome.** State what should be observably true when the work is
   complete. Create a task file only when the work is multi-step, spans
   sessions, or needs durable acceptance checks.
3. **Investigate.** Locate the affected code, interfaces, tests, and constraints.
   Resolve uncertainty with focused inspection or a small experiment. Record
   current and target states only when they differ.
4. **Implement.** Make the smallest coherent change that satisfies the outcome.
   Keep interfaces clean and avoid unrelated refactors.
5. **Verify.** Run the most focused relevant checks first, followed by broader
   project checks when the risk warrants them. Confirm task acceptance checks
   and inspect the final diff.
6. **Reconcile.** Update planning, architecture, testing, and workflow documents
   made inaccurate by the change. Maintain the current branch's detail log and
   add only durable outcomes to the summary log.
7. **Integrate.** Follow `version-control.md`, including its pre-merge PR
   deployment and integrated-test gate. Leave the worktree understandable, and
   report the result, verification performed, and any remaining work.

If blocked, preserve the evidence and next useful action in the task or log. Do
not add process artifacts when a concise note is enough.
