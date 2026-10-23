# Bead: sase-1nn.4 — Make the custom gate modal sizing tests deterministic

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.137](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.137.md) · **Assignee:** `sase-1nn.4` · **Size:** small
**Created:** 2026-10-23 11:30:06 EDT · **Closed:** 2026-10-23 12:27:44 EDT
**Plan:** [202610/v0\_18\_1\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release.md)

## Description

modal-sizing: replace pause-then-assert resize checks in test_custom_gate_modal_sizing.py with waits on the settled layout so Master Gate shard 8 goes green.

## Notes

[2026-10-23T16:27:31Z · sase-1nn.4] PROPOSED FOLLOW-UP: sase tool run check exit 1 is no_new_failures with 4 KNOWN on this tree and on clean HEAD (git stash): test_tui_app_import_stays_under_startup_budget 3529 vs cap 3527 (+0 sase.* vs merge-base, tracked by sase-1ic); test_gc_policy::test_freeze_happens_once and test_census_off_by_default (witnesses 399cf5928cebd2fc5752cf5069e2aef7 / 0565caed0d1ee997557a16ec01dc1ecb); test_statistics_perf::test_populated_perf_renderable_covers_every_panel missing "SASE_TUI_PERF off". Same cluster already noted on sase-1nn.3.

[2026-10-23T16:27:44Z · sase-1nn.4] Replaced pause-then-assert after resize in test_custom_gate_modal_sizing.py with wait_for on terminal size, mounted shell, shell width, footer fit, scroll height, and rail dock/width. Compact scroll re-fits after the resize frame when max-height changes. Sibling test_custom_gate_* files have no resize_terminal. Proof: 20/20 serial file passes; tests/ace/tui/ -n 8 once (sizing nodes passed; run stopped on unrelated KNOWN); two more -n 8 custom-gate+neighbor passes 78/78. sase tool run check lint green, tests no_new_failures (4 KNOWN on clean HEAD too).

## Dependencies

- **Blocks:** [sase-1nn.5](sase-1nn.5.md) ✓ · ⧖ 2026-10-23
- **Blocks:** [sase-1nn.7](sase-1nn.7.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.4/README.md) | [sase-1nn.4](sase-1nn.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a3a702`](https://github.com/sase-org/sase/commit/1a3a7022d1878b395a36f67a2837546dca2684ea) | fix(ace): wait for settled custom-gate modal geometry after resize | [sase-1nn.4](sase-1nn.4.md) | 2026-10-23 12:29:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2a.cld][1] | E3 readiness: sase-1nn status | 1 |
| read-by | [agent:sase-1nn.4][2] | Need full notes, remaining work, and design file path | 2 |
| read-by | [agent:sase-1nn.6][3] | Need sibling phase close notes and epic status before Full CI triage | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2a.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.6/README.md

<!-- sase:referenced-by:end -->
