# Version-control workflow

Use trunk-based development. `main` is the trunk and should remain releasable.

## Working rules

- Integrate small, complete changes frequently. Avoid long-lived development,
  release, or integration branches.
- Work directly on `main` for low-risk solo changes when repository policy
  permits it. Otherwise use a short-lived branch and merge it promptly.
- Keep commits focused and describe the outcome in the commit message. A
  formal commit-message convention is optional unless the project adopts one.
- Sync with `origin/main` before integrating. Resolve conflicts on the working
  branch and rerun affected checks.
- Never force-push `main`. Do not rewrite commits already shared with others
  unless coordination and repository policy explicitly allow it.
- Preserve unrelated local changes. Do not discard or include someone else's
  work in a commit without authorization.
- Keep credentials, generated runtime state, and large disposable artifacts out
  of version control.

## Typical loop

1. Confirm the worktree state with `git status` and update local knowledge of
   the remote.
2. Start from current `main` or create a short-lived branch from it.
3. Make one coherent change and run the appropriate checks.
4. Review the diff, then commit only the files belonging to that change.
5. Bring the branch up to date with `origin/main` and verify again if the update
   changes the tested result.
6. Push and integrate through the repository's required review process. Delete
   the short-lived branch after integration.

For incomplete work that must reach `main`, keep it safe behind a feature flag
or another inactive path. Create releases from known commits on `main`, using
tags when a durable release identifier is needed. Apply urgent fixes to `main`
first so later releases do not lose them.
