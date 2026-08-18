# Version-control workflow

Use trunk-based development. `main` is the trunk and should remain releasable.

## Working rules

- Integrate small, complete changes frequently. Avoid long-lived development,
  release, or integration branches.
- Start each change from current `main` on a short-lived `feature/` or `bug/`
  branch. Do not perform development directly on `main`.
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

1. **Branch from `main`.** Confirm the worktree state, update local knowledge of
   the remote, and create a short-lived `feature/` or `bug/` branch from current
   `main`.
2. **Develop locally.** Work in that branch until the functionality is
   satisfactory locally. Keep commits focused and run the relevant local tests.
3. **Reconcile with upstream.** Check for changes in `origin/main`. If it has
   advanced, rebase the branch onto it, resolve conflicts in the branch, and
   smoke-test the rebased result locally.
4. **Open or update a pull request.** When the branch is current and local
   checks pass, push it and open a pull request to `main`, or update the existing
   pull request when repeating the loop.
5. **Test the deployed branch.** Deploy the exact pull-request revision to test
   infrastructure and run the relevant integrated tests, including affected
   migrations, service boundaries, and external integrations. Prefer an
   isolated preview environment; when using shared infrastructure, identify the
   deployed revision and avoid colliding with other tests.
6. **Merge and deploy.** If integrated testing passes, merge the branch into
   `main`, deploy the merged `main` revision to production, confirm the trunk
   and deployment checks, then remove the test deployment and delete the
   branch. If integrated testing fails, return to step 2, fix the branch, and
   repeat the upstream, local-test, PR, and deployed-test steps.

The PR deployment and integrated-test result are pre-merge evidence. Keep the
result discoverable from the pull request or its checks. Any change to the
tested revision invalidates that evidence and must be redeployed and retested.
Do not expose credentials, production data, or other secrets in logs or
artifacts.

For incomplete work that must reach `main`, keep it safe behind a feature flag
or another inactive path and still run the full loop. Create releases from known
commits on `main`, using tags when a durable release identifier is needed. Put
urgent fixes through the same `bug/` branch workflow and prioritize their merge
into `main` so later releases do not lose them.
