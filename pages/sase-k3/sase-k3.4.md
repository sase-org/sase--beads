# Bead: sase-k3.4 — Read-only freshness policy for ACE's Tier-1 index query

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.4` · **Size:** medium
**Created:** 2026-08-12 11:37:58 EDT · **Closed:** 2026-08-12 13:41:40 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

repair: add a freshness knob to the artifact-index query wire in sase-core so ACE's startup and auto-refresh queries skip hidden-row repair and per-row marker revalidation, stop selecting record_json in refresh_stale_rows, and run one coalesced revalidating reconcile after first paint on a long cadence.

## Notes

[2026-08-12T17:41:40Z · sase-k3.4] Verified freshness=cached/read-only Tier-1 path: Rust core cached queries skip repair/revalidation/upserts and refresh_stale_rows no longer selects record_json; ACE Tier-1 uses cached with deferred post-paint revalidate; verified sase-core just check, focused Python tests 48 passed, main lint/validation via just check plus direct just test-scoped full lane 29205 passed/10 skipped, git diff --check clean in both repos.

[2026-08-12T17:42:57Z · sase-k3.4] Verified sase-core just check; main repo focused pytest passed; main just test-scoped escalated to the full lane and passed 29205 passed, 10 skipped; git diff --check clean in both repos.

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.4/README.md) | [sase-k3.4](sase-k3.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@61cc793`](https://github.com/sase-org/sase-core/commit/61cc7937e08e0d4cb629a1e04cf79cddd7924f3f) | perf(agent-scan): add cached artifact index freshness mode | [sase-k3.4](sase-k3.4.md) | 2026-08-12 13:51:20 EDT |
| sase | [`8f9c5c3`](https://github.com/sase-org/sase/commit/8f9c5c3ff30a424fc8c7236f2d13fa319afe4895) | perf(ace): use cached Tier 1 artifact index loads | [sase-k3.4](sase-k3.4.md) | 2026-08-12 13:52:24 EDT |
