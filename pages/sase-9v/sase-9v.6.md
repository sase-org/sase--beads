# Bead: sase-9v.6 — Fit the bead\_store\_refresh chop inside its own time budget

[Bead Pages](../README.md) / [sase-9v](README.md) / sase-9v.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9v.6` · **Size:** small
**Created:** 2026-07-26 15:32:22 UTC · **Closed:** 2026-07-26 16:23:22 UTC
**Plan:** [sase/repos/plans/202607/bead\_review\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/bead_review_hardening.md)

## Description

refresh_chop_budget: bound the per-project lock wait of the chop's blocking refresh below the chop timeout, and persist backoff state so a timeout kill does not erase it; scoped to compose with the separately planned sase-9u refresh_cooldown phase.

## Notes

refresh_chop_budget landed.

Implementation:
- refresh_bead_store(beads_dir, *, lock_timeout=None) threads the bound into its
  existing store_git_write_lock acquisition (no parallel path); default None keeps
  the 180s worktree-mutation bound for every other caller.
- The chop derives its own budget from _CHOP_TIMEOUT_SECONDS=120 (kept in sync with
  default_config.yml): each waiting project gets an equal slice of a 60s lock-wait
  budget with a 10s floor, and the pass defers any project still unattempted after
  a 90s work budget (new stores_deferred counter / budget_exhausted reason).
- The backoff entry is now persisted BEFORE the refresh attempt and deleted after a
  success, so a chop-timeout SIGKILL leaves a backoff record instead of erasing it.

sase-9u refresh_cooldown composition (for whoever lands second): this phase touched
only the lock-wait bound in refresh_bead_store and the backoff write ordering in
sase_chop_bead_store_refresh._run. It adds no cooldown/TTL gating, so 9u should add
its gate as a pre-attempt skip in the same loop (before the backoff pre-write at the
canonical_beads_dir_for_project block) and leave the lock_timeout kwarg alone. Note
that the pre-write means a project skipped by a 9u cooldown must NOT get an in-flight
backoff entry.

Phase-5 (sync_worker_hygiene) overlap: its backoff-pruning bullet touches the same
_run loop and will rebase over the new pre-write/delete calls.

Not done here (out of scope, unchanged): the pre-existing ordering in refresh_bead_store
where the integration-marker generation check runs before the `acquired` check.

just check: all lint/format/symvision/validation steps green; test failures were
load-induced flakes (different set each run, none in bead code) that pass individually.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9v.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9v.6/README.md) | [sase-9v.6](sase-9v.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`54f4203`](https://github.com/sase-org/sase/commit/54f42034b81f28bc6b08294c43505cec8c2b2890) | fix(axe): fit bead\_store\_refresh chop inside its time budget (sase-9v.6) | [sase-9v.6](sase-9v.6.md) | 2026-07-26 16:26:16 |
