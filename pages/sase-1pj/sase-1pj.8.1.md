# Bead: sase-1pj.8.1 — Retire the staged-handoff kill protocol

[Bead Pages](../README.md) / [sase-1pj.8](sase-1pj.8.md) / sase-1pj.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.md) · **Assignee:** `sase-1pj.8.1.land`
**Created:** 2026-11-02 20:59:31 EST · **Closed:** 2026-11-03 10:46:56 EST
**Plan:** [202611/retire\_staged\_handoff\_kill\_path.md](https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/retire_staged_handoff_kill_path.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/retire_staged_handoff_kill_path.md

<!-- sase:links:end -->

## Description

Make every in-agent handoff stage for host completion, remove obsolete kill recovery, and score declarations correctly without losing historical evidence.

## Notes

[2026-11-03T15:14:50Z · sase-1pj.8.1.land] LAND TRIAGE (sase-1pj.8.1.land): PROPOSED FOLLOW-UP outcomes. (1) sase-1pj.8.1.1 note #1, multi-hop staged pipe adoption: ACCEPTED AS REMAINING EPIC WORK, not a task. Reproduced on bdbbce02e3 with a two-hop staged pipe through tests/fakey harness; the second adoption raises StagedHandoffError 'persisted agent identity differs from the active runner identity' (src/sase/axe/run_agent_exec_staged_adopters.py:28) because inline agent-session successors keep the runner ctx.agent_name while their agent_meta name is <base>--<n>. Before this epic the default (flag-off) kill path handled multi-hop pipes; f4254582d8 removed that path and cut the two-hop chain test down to one hop, so the regression is epic-caused. The same check also blocks gate/questions/plan/monitor staged by any in-process successor. (2) sase-1pj.8.1.7 notes #5/#6, prepared-monitor completion refuses after monitor staging promotes the starter identity (prepared_creator_agent_mismatch, then missing SASE_FINAL_TURN_NONCE): DECLINED as epic work and recorded as a DISCOVERED ISSUE note on the causally related active epic sase-1pj, because it stems from sase-1pj.5 staging-time promotion plus sase-core prepared-coverage identity checks that this epic did not change. No duplicate task exists; sase-1qm (stale_worktree_fingerprint) is related but a different defect. Verification also found the runtime-retirement phase left dead kill-only adopter branches (interrupted, persist_chat, reset_killed_state, require_capture, staged_id=None pipe paths) kept alive only by tests/_legacy_handoff_markers.py, which the plan required removing. That is remaining epic work too. sase-1pj.8 has no PROPOSED FOLLOW-UP notes.

[2026-11-03T15:46:56Z · sase-1pj.8.1.land] Finish retire kill-path landing: all seven phases verified (f4254582d8, 11147ccf2f, 671431ee80, 8caa3fd1f5, d3518e567d, fdad1aa7bf); staged_handoffs flag and sase-1pk retired; readout core pin and binding verified; agent-hijack (01a28287c8, f163ba74c0, 8ac56e2a09, aa7eedb1c5) and readout/runner splits (323a91d69f, d191279c26) integrated. Fixed inline-successor regression: in-process member (base+suffix with session match) now adopts for pipe/gate/monitor/plan/questions, ctx keeps session base so second pipe hop creates fakey-e2e--2 depth 2 piped_from --1; settlement accepts member. Restored two-hop pipe e2e (max_chain=2, --2 depth2, bound refusal, no STAGED file). Retired dead kill-only branches (interrupted/persist_chat/reset_killed/require_capture/staged_id None) and migrated 106 legacy marker calls to staged entry points with real responses; archived fixtures only via write_legacy. Follow-ups: multi-hop fixed as epic work; 8.1.7 prepared-monitor identity recorded as DISCOVERED on sase-1pj (not epic work). Check ToolRun 09cb7869273dd32b71efb5a400e872e8 (ruff/symvision clean; mypy INTERNAL ERROR in agents_sync pre-existing, unrelated). Focused: pipe e2e 1 passed, pipe unit 2 passed, inprocess adoption 7 passed, monitor 695 passed, plan followup 103 passed, staged reconcile 64 passed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.8.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.1.land.md) | [sase-1pj.8.1](sase-1pj.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ced5901`](https://github.com/sase-org/sase/commit/ced5901dd5612f00f767b3e7bc695a0936bdc14f) | feat(axe): finish staged-handoff kill-path landing | [sase-1pj.8.1](sase-1pj.8.1.md) | 2026-11-03 10:50:37 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.8.1.1][1] | Need the parent epic decisions governing this phase | 1 |
| read-by | [agent:sase-1pj.8.1.3--2][2] | Need epic DECISIONS and remaining phase context | 1 |
| read-by | [agent:sase-1pj.8.1.4][3] | Need parent epic DECISIONS and remaining notes | 1 |
| read-by | [agent:sase-1pj.8.1.6][4] | parent epic scope and decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.8.1.3.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.8.1.6/README.md

<!-- sase:referenced-by:end -->
