# Bead: sase-1pu.5.1.5.1 — Complete raw-evidence and bounded-discovery contracts in Rust

[Bead Pages](../README.md) / [sase-1pu.5.1.5](sase-1pu.5.1.5.md) / sase-1pu.5.1.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.land.md) · **Assignee:** `sase-1pu.5.1.5.1` · **Size:** medium
**Created:** 2026-11-01 10:17:41 EST · **Closed:** 2026-11-01 10:46:02 EST
**Plan:** [202611/published\_state\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/published_state_landing_repairs.md)

## Description

evidence-policy: implement shared raw-marker classification and bounded hood-discovery contracts described below in sase-core, including registered bindings and tests. Reuse the existing terminal precedence and scheduler policy. Record the host-created core commit for the dependent Python phase.

## Notes

[2026-11-01T15:45:10Z · sase-1pu.5.1.5.1] PROPOSED FOLLOW-UP: Coordinate the clean-base staged_handoff rustfmt failure with existing owner epic sase-1pj.6.1#2 — ToolRun f67af1ce29377847573102c786729866 (`sase tool run check`) at core HEAD 764317b9 fails only on rustfmt diffs in four staged_handoff files that were clean at phase start and are untouched here. Existing active owner epic now has the independent reproduction; no new task bead created.

[2026-11-01T15:45:53Z · sase-1pu.5.1.5.1] CORE COMMIT: The host-owned finalizer commit for these linked sase-core changes is the dependent phase prerequisite. The checkout was based on 764317b9 before this work; phase 2 should use the containing commit produced by this turn, not that base SHA. The commit SHA is assigned by host finalization.

[2026-11-01T15:46:02Z · sase-1pu.5.1.5.1] Implemented the typed raw-observation resolver and bounded hood/run discovery wire contracts in sase-core, including registered Python bindings. Verified just test -p sase_core agent_run_state (21 passed), just test -p sase_core_py agent_run_state (2 passed), and git diff --check. Required epic-symbol check returned no entries. sase tool run check ToolRun f67af1ce29377847573102c786729866 failed only on rustfmt diffs in four unchanged staged_handoff files; recorded as a clean-base PROPOSED FOLLOW-UP and on existing owner epic sase-1pj.6.1. The dependent phase should consume the host-finalizer commit recorded in this phase's note.

## Dependencies

- **Blocks:** [sase-1pu.5.1.5.2](sase-1pu.5.1.5.2.md) ✓ · ⧖ 2026-11-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.5.1.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.5.1.5.1/README.md) | [sase-1pu.5.1.5.1](sase-1pu.5.1.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dc5383f`](https://github.com/sase-org/sase-core/commit/dc5383f6cb3008b2b6dc935b13afba5679d17787) | feat(agent-run-state): classify raw evidence and bound hood discovery | [sase-1pu.5.1.5.1](sase-1pu.5.1.5.1.md) | 2026-11-01 10:46:47 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.5.1.5.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.5.1.5.1/README.md

<!-- sase:referenced-by:end -->
