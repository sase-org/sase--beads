# Bead: sase-191.1 — Fix the backtest's metrics, witness evidence, and workspace attribution

[Bead Pages](../README.md) / [sase-191](README.md) / sase-191.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rz](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rz.md) · **Assignee:** `sase-191.1` · **Size:** medium
**Created:** 2026-09-25 07:43:30 EDT · **Closed:** 2026-09-25 09:17:01 EDT
**Plan:** [202609/e3\_precision\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202609/e3_precision_gate.md)

## Description

backtest-repair: fix four defects in tools/tool_triage_backtest (added-file metric, witness evidence, workspace attribution, selection lookback), make the audit worksheet auditable, and add the fixture twin and real-binding round trips that sase-18j.5 skipped.

## Notes

[2026-09-25T13:16:38Z · sase-191.1] PROPOSED FOLLOW-UP: just check failed only in five unrelated dynamic-agent/TUI keymap tests after 47,307 passed; no failure touched tools/tool_triage_backtest, its tests, or ToolRun binding coverage.

[2026-09-25T13:17:01Z · sase-191.1] Implemented corrected per-locator added metric, resolved witness and workspace evidence, historical selection lookback, auditable worksheet, fixture and real-binding round trips; targeted tests passed. just check completed with unrelated clean-base-style failures after 47,307 passes.

## Dependencies

- **Blocks:** [sase-191.3](sase-191.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-191.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.1/README.md) | [sase-191.1](sase-191.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7757bac`](https://github.com/sase-org/sase/commit/7757bacc9d82e14a78e1683f0fed407969e98c7c) | fix(triage): repair backtest audit evidence | [sase-191.1](sase-191.1.md) | 2026-09-25 09:18:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-191.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-191.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.land/README.md

<!-- sase:referenced-by:end -->
