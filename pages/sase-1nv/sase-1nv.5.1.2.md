# Bead: sase-1nv.5.1.2 — Expose exact publication retries through the existing CLI

[Bead Pages](../README.md) / [sase-1nv.5.1](sase-1nv.5.1.md) / sase-1nv.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nv.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.5.md) · **Assignee:** `sase-1nv.5.1.2` · **Size:** medium
**Created:** 2026-10-26 18:05:04 EDT · **Closed:** 2026-10-26 19:50:53 EDT
**Plan:** [202610/finish\_publication\_recovery\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_publication_recovery_proof.md)

## Description

targeted-cli: wire the landed Rust selection into sase agent sync, add parser and real-outbox regression coverage, document the option, and ratchet the core pin.

## Notes

[2026-10-26T23:50:35Z · sase-1nv.5.1.2] PROPOSED FOLLOW-UP: three capacity tests fail identically on clean master — test_capacity_blocked_waiter_does_not_park_the_queue_behind_it and test_capacity_blocked_head_then_high_budget_launch_uses_real_scan (assert drained is None got unexpected) plus test_capacity_only_skips_done_dirs_and_keeps_active_ones (KNOWN witness 98bebed7687074511ffc5349e99a72f7); no existing task bead found

[2026-10-26T23:50:53Z · sase-1nv.5.1.2] Wired --retry-key/-k through parser, handle_agents_sync, sync_agents, select_and_revive, and the Rust exact_key facade. Parser/handler tests plus real-outbox regressions pass: stopped timeout is selected behind unrelated active/quarantined/retired/referenced-by rows, missing keys are no-ops, no substitution. Documented in agents-sidecar-sync.md, hood-sync.md, and generated CLI. Completion spec and retry_key text hint updated. sase-core-revision.txt already at HEAD b12e5815 (includes ae38a60e exact-key). just rust-install installed the workspace binding. sase tool run check de8296a5: lint/docs green; 3 completion failures fixed after; 3 capacity tests fail identically on clean master (PROPOSED FOLLOW-UP). epic-symbols: none. No production retry.

## Dependencies

- **Depends on:** [sase-1nv.5.1.1](sase-1nv.5.1.1.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1nv.5.1.3](sase-1nv.5.1.3.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.2/README.md) | [sase-1nv.5.1.2](sase-1nv.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aa97e54`](https://github.com/sase-org/sase/commit/aa97e544b0e68c0f1c0211bdfb75cf1b0b3e48d1) | feat(agents-sync): add --retry-key for exact publication retries | [sase-1nv.5.1.2](sase-1nv.5.1.2.md) | 2026-10-26 19:53:11 EDT |
