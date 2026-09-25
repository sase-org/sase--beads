# Bead: sase-18j.5 — Pin the core, gather triage inputs, and pass the precision backtest

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.5` · **Size:** large
**Created:** 2026-09-24 19:07:08 EDT · **Closed:** 2026-09-25 10:11:13 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:88153ff59741b262232d81de | attached via sase artifact create --bead |
| related | file:explicit:a6279075b0c1d3b4e652949c | attached via sase artifact create --bead |
| related | file:explicit:ef446cbbb5df4283a4022132 | attached via sase artifact create --bead |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

bindings-and-backtest: move the core pin and add adapters and validators for every new binding, build the bounded input gatherers, write tools/tool_triage_backtest, and pass the at-least-95% hand-audited KNOWN precision gate on athena before any label is stored.

## Notes

[2026-09-25T02:43:39Z · sase-18j.5--3] PROPOSED FOLLOW-UP: Repair the precision backtest's KNOWN-on-added/untracked safeguard. The clean-witness replay (--sample 60 --min-witnesses 2 --touched-requires-clean-witness) produced 313 KNOWN items, 139 on added/untracked paths, and 0 KNOWN-but-touched; DoD-5 requires at least 95% hand-audited KNOWN precision and zero added-file KNOWN. Preserve and use file:explicit:88153ff59741b262232d81de (report) and file:explicit:959535d805b6acd19d053edb (audit worksheet), then rerun the backtest before changing final classifier constants or storing any labels.

[2026-09-25T14:01:22Z · sase-191.3] DoD-5 PRECISION GATE: PASS on round 1 (seed 7, default knobs min_witnesses=1, touched_requires_clean_witness=false). 578 selected runs; labels known=3096 (symvision 2491, mypy 245, pytest/scoped 354, toobig 6), new=673, unknown=188 (no_witness 113, untouched_no_pass_witness 113, extractor_generic 75), flaky=15. known_on_added_or_untracked=0 (per-locator metric; informational any-path count known_items_in_runs_with_untracked_paths=1680). Hand audit: 60/60 sampled KNOWN pre-existing (53 symvision, 5 pytest, 2 mypy) + 17/17 KNOWN-but-touched dispositioned pre-existing = 77/77 (100% >= 95%). Workspace attribution ledger=19/agent_meta=511/none=48 (8%). Knobs unchanged (src/sase/tool/triage_inputs.py MIN_WITNESSES=1, TOUCHED_REQUIRES_CLEAN_WITNESS=False). Artifacts file:explicit:ef446cbbb5df4283a4022132 (report) and file:explicit:a6279075b0c1d3b4e652949c (filled audit). Pin c558f88942a155349ee76d6689abd4f9734bcf5f with workspace recording live since cdcbcdd9d. Note #1s 139 was the any-path metric (defect 1): 0 sampled locators were on added/untracked files. No failed rounds. -r precision-gate evidence

[2026-09-25T14:11:13Z · sase-191.3] DoD-5 precision gate PASS: round-1 backtest (seed 7, min_witnesses=1, no clean-witness requirement) over 578 runs; 60/60 sampled KNOWN + 17/17 KNOWN-but-touched hand-audited pre-existing (100%); known_on_added_or_untracked=0; attribution none=8%. Knobs unchanged (MIN_WITNESSES=1, TOUCHED_REQUIRES_CLEAN_WITNESS=False). Evidence file:explicit:ef446cbbb5df4283a4022132 + file:explicit:a6279075b0c1d3b4e652949c. Pin c558f88942a15; workspace recording live since cdcbcdd9d. Note-139 explained as the any-path metric. Owner-matching over-match filed as DISCOVERED ISSUE on sase-18j/sase-18j.6 + follow-up on sase-191.3. sase tool run check green.

## References

- file:explicit:88153ff59741b262232d81de
- file:explicit:959535d805b6acd19d053edb

## Dependencies

- **Depends on:** [sase-18j.1](sase-18j.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18j.3](sase-18j.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18j.6](sase-18j.6.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-18j.5.md) | [sase-18j.5](sase-18j.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cdcbcdd`](https://github.com/sase-org/sase/commit/cdcbcdd9d3988359f1b4fc77d6d0454632a4e760) | feat(tool): add triage input backtest | [sase-18j.5](sase-18j.5.md) | 2026-09-24 22:45:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.land][1] | Check whether the phase that landed the triage backtest is still active and plans its references | 1 |
| read-by | [agent:sase-18j.5--3][2] | Need phase scope and notes before recording the E3 gate outcome | 2 |
| read-by | [agent:sase-191.land][3] | Landing check: gate note and closed state | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-18j.5.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.land/README.md

<!-- sase:referenced-by:end -->
