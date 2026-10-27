# Bead: sase-1oh.4.1.1 — Add atomic Rust recovery of closes owned by a failed run

[Bead Pages](../README.md) / [sase-1oh.4.1](sase-1oh.4.1.md) / sase-1oh.4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.4.md) · **Assignee:** `sase-1oh.4.1.1` · **Size:** medium
**Created:** 2026-10-26 14:34:47 EDT · **Closed:** 2026-10-26 15:39:56 EDT
**Plan:** [202610/failed\_stitch\_bead\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/failed_stitch_bead_recovery.md)

## Description

recovery-core: add close provenance, durable completion-failure facts, and an idempotent Rust mutation that conditionally reopens this run's standing done closes with their ancestors and a STITCH FAILED note. Expose tested bindings; implement the failure-fact classification in the Rust stranded-work reducer.

## Notes

[2026-10-26T19:39:47Z · sase-1oh.4.1.1] Implemented provenance-backed failed-stitch recovery in sase-core, including recover_failed_closes, the PyO3 bead_recover_failed_closes binding, and bead_close(close_provenance=...). Added close-history event IDs and failed completion facts to stranded-work classification. Verification: just fmt, just fast, focused completion_recovery (3), stranded_work (26), failed_close_recovery_binding (1), replay_goldens (2), doctor projection parity (1), and final sase tool run check all passed.

[2026-10-26T19:39:56Z · sase-1oh.4.1.1] Implemented provenance-backed recovery for failed-run closes, with recover_failed_closes plus the PyO3 bead_recover_failed_closes and bead_close(close_provenance=...) bindings. Focused recovery, stranded-work, binding, replay-golden, and projection-parity tests passed; final sase tool run check succeeded (3b12888f83f5c1e4262f6eceb7334dbf). epic-symbol scan found no leftovers.

## Dependencies

- **Blocks:** [sase-1oh.4.1.2](sase-1oh.4.1.2.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oh.4.1.3](sase-1oh.4.1.3.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oh.4.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.1/README.md) | [sase-1oh.4.1.1](sase-1oh.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4f17b72`](https://github.com/sase-org/sase-core/commit/4f17b727bdbff69515a5cebc5db099ca549edf98) | feat(beads): recover failed-run closes atomically | [sase-1oh.4.1.1](sase-1oh.4.1.1.md) | 2026-10-26 15:40:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oh.4.1.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1oh.4.1.2][2] | need landed core API binding names | 1 |
| read-by | [agent:sase-1oh.4.1.3][3] | Need recovery-core binding names and close evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.4.1.3/README.md

<!-- sase:referenced-by:end -->
