# Bead: sase-1t3.13.1.3 — Limit periodic work to surfaced rows and relevant waiters

[Bead Pages](../README.md) / [sase-1t3.13.1](sase-1t3.13.1.md) / sase-1t3.13.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t3.13](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.md) · **Assignee:** `sase-1t3.13.1.3` · **Size:** medium
**Created:** 2026-11-18 15:37:14 EST · **Closed:** 2026-11-18 17:04:07 EST
**Plan:** [202611/interaction\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202611/interaction_latency.md)

## Description

visible-work: share a viewport-aware row selection between runtime ticks and bead warmup, retain wait-status correctness, and make stranded sweeps lazy; preserve the existing Rust interval-union semantics and cache bounds.

## Notes

[2026-11-18T22:03:44Z · sase-1t3.13.1.3--1] ## Verification evidence — visible-work

Environment: Python 3.14.7, Textual 8.0.1, sase 0.19.0, sase-core-rs 0.44.2; current sase-core-revision.txt pin 7ac2081. The baseline phase used the same Python/Textual/sase versions and recorded tick/warmup predicate scan ratios of 4.1x at 150 rows and 16.3x at 600 rows, supporting viewport and waiter bounding.

Changed paths: src/sase/ace/tui/actions/_event_countdown.py, _state_init_runtime.py, _stranded_resolve_actions.py, actions/agents/_loading_bead_warmup.py, widgets/_agent_list_widget.py, tests/ace/tui/test_agents_bead_warmup.py, test_stranded_resolve_actions.py, and widgets/test_agent_list_runtime_patching.py.

Verification: sase_core_rs imports from the venv. just fmt passed. After the widget-query fallback correction, the combined named-proc, warmup, stranded-action, and runtime-patching tests passed: 60 passed in 5.82s. git diff --check passed. The original sase tool run check 70f2292dbe1db0c44772b9b47d114124 passed every lint and SASE validation stage, then exited 1 in its escalated full test lane: 61,999 passed, 18 skipped, 8 failed. Six named-proc failures came from the selector querying an unmounted test fake; the fallback was fixed and all those tests passed in the 60-test rerun. The two remaining check failures were checked against clean HEAD bd8616817d90d840b68ba5858bf44af12f9d1573: test_failed_parent_and_step_parity reproduced with compact step_output {} instead of {meta_note: kept}; test_blocked_render_with_young_index_lock_is_bounded passed in 1.75s after failing at 4.36s under the 14-worker full run. Searches found no existing task beads for those failures.

Bounded-work evidence: with 40 rows and an 8-line viewport, the runtime test selects and patches only the two surfaced rows; scrolling moves the selection to later rows without overlap. With 80 historical WAITING rows, warmup selects at most 32 per batch, and two batches cover 64 distinct identities. Each stranded batch is bounded to four due projects while the cursor continues the background sweep in 16-project increments. No live-host timing rerun was captured; these bounds are asserted by the focused tests.

PROPOSED FOLLOW-UP: Triage the baseline compact workflow parity failure — it reproduces on clean HEAD bd861681; no existing tracking bead was found.

PROPOSED FOLLOW-UP: Review the load-sensitive publication cleanup test — full-suite failure took 4.36s against a 2s bound, while the same test passed on clean HEAD in 1.75s; no existing tracking bead was found.

[2026-11-18T22:04:07Z · sase-1t3.13.1.3--1] Implemented viewport-bounded runtime patches and surfaced-row bead warmup with bounded WAITING and stranded sweeps. just fmt and 60 focused tests passed; epic-symbols is empty. Full check lint passed; two remaining test failures were recorded as proposed follow-ups after clean-base reproduction/pass evidence.

## Dependencies

- **Depends on:** [sase-1t3.13.1.1](sase-1t3.13.1.1.md) ✓ · ⧖ 2026-11-18
- **Blocks:** [sase-1t3.13.1.5](sase-1t3.13.1.5.md) ◐ · ⧖ 2026-11-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t3.13.1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.1.3.md) | [sase-1t3.13.1.3](sase-1t3.13.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f81ff92`](https://github.com/sase-org/sase/commit/f81ff92e0549150a29cdb5fe2cd2fa51930bb60a) | perf(ace): bound runtime and bead warmup work | [sase-1t3.13.1.3](sase-1t3.13.1.3.md) | 2026-11-18 17:06:19 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.13.1.3--1][1] | Need the phase scope, design file, decisions, and prior notes before continuing | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.13.1.3.md

<!-- sase:referenced-by:end -->
