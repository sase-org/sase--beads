# Bead: sase-1aq.10.7.5.7.4.1 — Commit the host\_liveness claims-cache recheck fix to sase-core

[Bead Pages](../README.md) / [sase-1aq.10.7.5.7.4](sase-1aq.10.7.5.7.4.md) / sase-1aq.10.7.5.7.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.5.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.7.land.md) · **Assignee:** `sase-1aq.10.7.5.7.4.1` · **Size:** small
**Created:** 2026-09-27 05:04:20 EDT · **Closed:** 2026-09-27 05:18:31 EDT
**Plan:** [202609/1aq\_land\_claims\_cache\_fix\_and\_reconverge.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_land_claims_cache_fix_and_reconverge.md)

## Description

land_claims_fix: apply the audited host_liveness.rs claims-cache recheck diff in the linked sase-core checkout with its regression test, run the focused cargo suites plus sase-core lint, and land it on sase-core master.

## Notes

[2026-09-27T09:17:54Z · sase-1aq.10.7.5.7.4.1] land_claims_fix verification: applied audited file:explicit:b02a5484229526d3fdf7cb20 via git apply (clean) to linked sase-core checkout at b57cd21; worktree file matches artifact byte-for-byte (+79/-9, one file). just test -p sase_core host_liveness: 13 passed (incl. new filesystem_probe_rechecks_stale_claims_before_mismatch). just test -p sase_core fleet_presentation: 18 passed. just test -p sase_gateway fleet_catalog_overlay: 1 passed. rustfmt --check on host_liveness.rs: clean. New regression test FAILS without the fix (IdentityMismatch vs Alive, proved in clean worktree) and passes with it. Change left uncommitted in linked checkout for the host finalizer to commit and land on sase-core master; no binding/wire change so no sase-core-revision.txt pin move needed.

[2026-09-27T09:18:07Z · sase-1aq.10.7.5.7.4.1] PROPOSED FOLLOW-UP: sase-core just check clippy gate is red on clean base b57cd21 (7 pre-existing errors: nonminimal_bool in agent_runtime.rs, maintenance.rs, fleet_owner_facts.rs, provider_usage/mod.rs x2, receipt.rs, triage.rs; manual RangeInclusive contains in maintenance.rs) — reproduced identically in a clean worktree without the fix, so unrelated to this phase; needs a clippy-cleanup task bead (toolchain 1.95.0 lints newer than the code).

[2026-09-27T09:18:31Z · sase-1aq.10.7.5.7.4.1] land_claims_fix done: audited claims-cache recheck diff applied to linked sase-core checkout (byte-identical to artifact, +79/-9), 13 host_liveness + 18 fleet_presentation + 1 gateway overlay tests green, fmt clean, regression test proved to fail without the fix; uncommitted for host finalizer to land; full just check blocked only by 7 pre-existing clean-base clippy reds recorded as follow-up

## Dependencies

- **Blocks:** [sase-1aq.10.7.5.7.4.2](sase-1aq.10.7.5.7.4.2.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.7.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.7.4.1/README.md) | [sase-1aq.10.7.5.7.4.1](sase-1aq.10.7.5.7.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@da93d01`](https://github.com/sase-org/sase-core/commit/da93d014c1d16cacdaa7e5acac53cbb38c259dcf) | fix(fleet): recheck stale workspace claims before excluding live rows | [sase-1aq.10.7.5.7.4.1](sase-1aq.10.7.5.7.4.1.md) | 2026-09-27 05:19:39 EDT |
