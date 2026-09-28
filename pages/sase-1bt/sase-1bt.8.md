# Bead: sase-1bt.8 — Live run blocks - in-flight stages, pending stages, follow and hold

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.8` · **Size:** medium
**Created:** 2026-09-27 18:32:46 EDT · **Closed:** 2026-09-28 05:41:09 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

runs-card-live: make a live run's block progress in place with a pure 1 Hz elapsed repaint, a detail refetch only on glance drift, pending stages from the reference run, silent state, follow-versus-hold on new runs, and an in-place settle transition.

## Notes

[2026-09-28T09:40:16Z · sase-1bt.8] PROPOSED FOLLOW-UP: timezone display guard fails on base (blocks.py:164, view_vocabulary.py:131, update_gear/panel_state) — route witness/silent times through sase.core.time format_local (sase-1bp class)

[2026-09-28T09:40:35Z · sase-1bt.8] PROPOSED FOLLOW-UP: test_agent_header_panel test_expanded_overflowing_header_claims_half_page_scroll fails identically on clean base — triage as flake or layout bug

[2026-09-28T09:40:47Z · sase-1bt.8] PROPOSED FOLLOW-UP: live screenshot inspection still open — flag-on sase screenshot --keep of a real live check (e.g. scratch sase tool run -- sleep 120), capture twice >=10s apart for elapsed/bar growth, plus a silent run past 60s (SIGSTOP a sleep wrapper, then resume+stop); cutover sase-1bt.12 re-inspects live anyway

[2026-09-28T09:41:09Z · sase-1bt.8] runs-card-live done: live/silent outcome lines with k/n progress and elapsed/typ (deck.py), silent hint line (blocks.py), pure 1Hz repaint under FINAL live gate with refetch only on glance-token drift plus cursor reconcile for follow/hold/in-place settle (tool_runs/live.py, view.py), now_s threaded through document builds. Verified: 12 new tests in tests/ace/tui/test_tool_runs_live_blocks.py pass; scoped lane 2529 passed with only 2 failures that reproduce identically on clean base (timezone guard, header scroll); all lint gates incl. symvision/mypy green; epic-symbols clean. Live screenshot inspection left as PROPOSED FOLLOW-UP for cutover.

## Dependencies

- **Blocks:** [sase-1bt.12](sase-1bt.12.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bt.7](sase-1bt.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.8/README.md) | [sase-1bt.8](sase-1bt.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b409a5`](https://github.com/sase-org/sase/commit/5b409a5aa373f2b3f6b30a4de9f05acea9325459) | feat(runs-card): live run blocks with in-place progress, silent state, and follow/hold (sase-1bt.8) | [sase-1bt.8](sase-1bt.8.md) | 2026-09-28 05:43:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bt.8/README.md

<!-- sase:referenced-by:end -->
