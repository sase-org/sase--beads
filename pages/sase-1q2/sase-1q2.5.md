# Bead: sase-1q2.5 — Fix the suite-gate, nested-preservation, and remaining non-TUI reds

[Bead Pages](../README.md) / [sase-1q2](README.md) / sase-1q2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16e](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16e.md) · **Assignee:** `sase-1q2.5` · **Size:** medium
**Created:** 2026-10-30 12:37:07 EDT · **Closed:** 2026-10-30 14:07:51 EDT
**Plan:** [202610/v0\_19\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_19_0_release.md)

## Description

harness-reds: fix the suite-gate scratch repo's import closure and the nested-preservation error wrapping, then every other non-TUI red at the tip.

## Notes

[2026-10-30T18:07:51Z · sase-1q2.5] Suite-gate miniature now copies the real runner import closure (AST tests.* imports plus -p plugin strings) instead of a hand-written list, so tests._agent_artifact_marker_audit_helpers cannot drop out again. Nested discovery wraps every OSError — including Python 3.12/3.13 Path.exists() PermissionError on an unreadable parent — as PreservationError matching "enumerate".

Proof: 20 serial runs of the six suite-gate nodes plus test_enumeration_failure_is_refused all passed; 3x -n 8 of both changed files passed (18 each). Wrap reproduced on cpython 3.12.13 and 3.13.13. sase tool run check succeeded (eb2fa25dd5d8ca81fa9e192e794f8740). epic-symbols: none.

Left live sibling work alone: sase-1q2.3 (sync help, completion, agent load / sase-1ov); sase-1q2.4 (pager, footprint, import budget, visual). Left toobig-8w.publication_state_repair.0 queued. Re-inventory of latest completed Master Gate 41088893633 and Full CI 41059821743: other recent-reds (contract manifest, justfile lint lint, artifact directory audit, sdd git streaming) pass locally.

## Dependencies

- **Blocks:** [sase-1q2.6](sase-1q2.6.md) ✓ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q2.5/README.md) | [sase-1q2.5](sase-1q2.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dab2d70`](https://github.com/sase-org/sase/commit/dab2d701fbac135ff3e828b2d0efd330c5a19b47) | fix(workspace): wrap nested-repo enumeration errors and copy the runner import closure | [sase-1q2.5](sase-1q2.5.md) | 2026-10-30 14:09:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1q2.5][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q2.5/README.md

<!-- sase:referenced-by:end -->
