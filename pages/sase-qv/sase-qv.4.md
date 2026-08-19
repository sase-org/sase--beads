# Bead: sase-qv.4 — Agents tab and agent list coloring

[Bead Pages](../README.md) / [sase-qv](README.md) / sase-qv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.4` · **Size:** medium
**Created:** 2026-08-19 09:14:32 EDT · **Closed:** 2026-08-19 13:24:34 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

agents_tab: color the monitor status token by its pair accent in the ACE agent list, add the outcome glyphs that replace the retired success green, add a Status field to the prompt panel MONITOR section, and color the sase agent list STATUS badge.

## Notes

[2026-08-19T17:22:56Z · sase-qv.4] PROPOSED FOLLOW-UP: Re-key stale sase-qt.6 --epic-symbol Justfile entries — closed sase-qt.6 leftovers make just check fail at symvision; re-key to still-open sase-qt.8 or wire the mutation APIs and drop the whitelist.

[2026-08-19T17:23:12Z · sase-qv.4] PROPOSED FOLLOW-UP: Unused public classify_flat_query_tokens — sase-qy.1 exported it with only in-file + test use; later sase-qy phases should consume it or make it private so just check stays green after qt.6 symbols are cleaned.

[2026-08-19T17:23:28Z · sase-qv.4] PROPOSED FOLLOW-UP: just test-visual has 24 PNG mismatches outside this phase — footer leader, glossary, axe editor, copy-as, prompt stack, plan toast, at-reference, help, and notification goldens; monitor goldens for this phase were updated and pass.

[2026-08-19T17:23:51Z · sase-qv.4] PROPOSED FOLLOW-UP: Completion snapshot tests fail on this tree — tests/completion/test_snapshot.py argparse view drifted from the checked-in spec; not caused by agents_tab coloring.

[2026-08-19T17:24:07Z · sase-qv.4] PROPOSED FOLLOW-UP: Flake test_ace_page_fast_startup_is_structurally_quiet — failed once in a full-suite run with a leftover cancelled artifacts-project-choices task, then passed on rerun.

[2026-08-19T17:24:34Z · sase-qv.4] Agents-tab monitor status coloring is in. A row whose status matches either half of its recorded pair is styled with the pair accent (bold while live, red on failed/timeout/lost) plus outcome glyphs; STARTING members stay sky-blue; failed rows keep a single existing ✗/<code> or stalled ⚠. Prompt-panel MONITOR sections now show Status: start → stop above State. sase agent list colors the STATUS badge the same way and emits monitor_start_status/monitor_stop_status in JSON. Verified: 144 targeted tests; just test-scoped 3376 passed; just test-visual monitor goldens updated and 10/10 agents family snapshots passed (agents_family_conversation_monitor_120x40, agents_settled_monitor_lane_badge_120x40). just check lint is red only on stale closed sase-qt.6 --epic-symbol leftovers this phase did not add. No --epic-symbol entries remain on sase-qv.4.

[2026-08-19T17:27:58Z · sase-qv.4] Agents-tab monitor status coloring is in. A row whose status matches either half of its recorded pair is styled with the pair accent (bold while live, red on failed/timeout/lost) plus outcome glyphs; STARTING members stay sky-blue; failed rows keep a single existing ✗/<code> or stalled ⚠. Prompt-panel MONITOR sections now show Status: start → stop above State. sase agent list colors the STATUS badge the same way and emits monitor_start_status/monitor_stop_status in JSON. Verified: 144 targeted tests; just test-scoped 3376 passed; just test-visual monitor goldens updated and 10/10 agents family snapshots passed (agents_family_conversation_monitor_120x40, agents_settled_monitor_lane_badge_120x40). just check lint is red only on stale closed sase-qt.6 --epic-symbol leftovers this phase did not add. No --epic-symbol entries remain on sase-qv.4.

## Dependencies

- **Depends on:** [sase-qv.3](sase-qv.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qv.7](sase-qv.7.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.4/README.md) | [sase-qv.4](sase-qv.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`91c4323`](https://github.com/sase-org/sase/commit/91c432385a6a632726a1838072474a9c16703d29) | feat(agents): color monitor status by pair accent | [sase-qv.4](sase-qv.4.md) | 2026-08-19 13:30:19 EDT |
