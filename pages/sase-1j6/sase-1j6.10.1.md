# Bead: sase-1j6.10.1 — Restrict healer targets to skew-shaped failures and stop loud or phantom side effects

[Bead Pages](../README.md) / [sase-1j6.10](sase-1j6.10.md) / sase-1j6.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1j6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.land.md) · **Assignee:** `sase-1j6.10.1` · **Size:** medium
**Created:** 2026-10-10 08:09:06 EDT · **Closed:** 2026-10-10 09:06:29 EDT
**Plan:** [202610/finish\_update\_skew\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_update_skew_auto_restart.md)

## Description

sweep-safety: make the scheduler job and `run -p` consider only doorbells, in-flight recovery rows, skew-suspect rows, and recent legacy skew-shaped rows; never claim, write, or notify for any other failure; stop write_recovery from recreating missing or wiped artifacts dirs; delete doorbells once owned; make the disabled and paused paths resurface each silenced failure exactly once; trip the storm breaker once; keep idle ticks cheap.

## Notes

[2026-10-10T13:06:10Z · sase-1j6.10.1] PROPOSED FOLLOW-UP: check gate blocked by pre-existing flags-lint failure (rule 7: closed flag bead sase-zg still defines agents_unified_query) — reproduces identically on clean base

[2026-10-10T13:06:15Z · sase-1j6.10.1] PROPOSED FOLLOW-UP: scoped tests test_default_config_matches_public_schema and test_no_system_clock_display_sites fail identically on clean base — epic-caused, owned by runner-ux-fixes phase

[2026-10-10T13:06:20Z · sase-1j6.10.1] PROPOSED FOLLOW-UP: symvision flags unused ArtifactIndexProjection in src/sase/agents/catalog/_sources.py identically on clean base — pre-existing, not sweep-safety

[2026-10-10T13:06:29Z · sase-1j6.10.1] sweep-safety done: shared is_healer_candidate (doorbell/in-flight/skew-suspect/recent-legacy) filters run -p and job sweep via scan facade with history fallback; heal_one pre-check skips non-candidates with no ledger/write/notify; doorbells deleted at claim/skip/decline; no recovery claimed state; post-execute launched write dropped; write_recovery never creates dirs and dry-run writes nothing; declines quiet for non-silenced rows (quiet_declines=quiet); storm trips once with one escalation then quiet paused declines; disabled/paused path resurfaces silenced rows exactly once via stamp; ledger reads mtime-gated. Verified: 10 new sweep-safety tests pass; all 98 neighboring auto-restart tests pass; check gate green through mypy; symvision adds no new findings; flags-lint, 2 scoped tests, and 1 symvision finding reproduce identically on clean base (recorded as follow-ups); no epic-symbol entries remain.

## Dependencies

- **Blocks:** [sase-1j6.10.5](sase-1j6.10.5.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.1/README.md) | [sase-1j6.10.1](sase-1j6.10.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.10.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.10.1/README.md

<!-- sase:referenced-by:end -->
