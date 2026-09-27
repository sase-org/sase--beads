# Bead: sase-1bc.4 — %tab launch path, storage, query field, and completion

[Bead Pages](../README.md) / [sase-1bc](README.md) / sase-1bc.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0t4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0t4.md) · **Assignee:** `sase-1bc.4` · **Size:** large
**Created:** 2026-09-27 10:57:04 EDT · **Closed:** 2026-09-27 13:26:25 EDT
**Plan:** [202609/agents\_dynamic\_tabs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_dynamic_tabs.md)

## Description

tab-directive: bump the core pin; parse and validate %tab in Python; write agent_tab to meta, clan records, and session follow-ups with root-mismatch errors; preserve it across retry, revive, and fork; load it into the Agent model from meta, index, and fleet rows; add the tab: query field and %tab completion; update docs and the xprompts memory table.

## Notes

[2026-09-27T17:25:55Z · sase-1bc.4] PROPOSED FOLLOW-UP: clan record schema has no clan_tab — add it beside tribe on ClanGenerationRecordWire, ClanRecordUpdateWire, and ClanLaunchDefaultsWire, then write it from record_clan_attributes_at_launch and inherit it in apply_clan_launch_defaults so a new generation keeps the tab after the declarer artifacts directory is gone.

[2026-09-27T17:26:09Z · sase-1bc.4] PROPOSED FOLLOW-UP: just check symvision reports 56 NEW unused public symbols (RunView*, DeckSpec, etc.) that also fail on the clean tree against the same linked sase-core checkout; cite sase-1ab.10.4 for the turn-rename pin bump. Closing tab-directive anyway per plan.

[2026-09-27T17:26:25Z · sase-1bc.4] Pin 0e8981a1f131d2dd040c4887ae949edf19fbeef6: %tab stored on agent_meta, loaded onto Agent from meta/index/fleet rows, queryable as tab: (main for default), stripped from model prompt; clan-record clan_tab follow-up recorded.

## Dependencies

- **Depends on:** [sase-1bc.3](sase-1bc.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.5](sase-1bc.5.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6](sase-1bc.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.4.md) | [sase-1bc.4](sase-1bc.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`372ecc9`](https://github.com/sase-org/sase/commit/372ecc97c36ae7b7b25edb10a35b6ccf6da3e958) | feat(xprompt): implement %tab directive for agent tab naming | [sase-1bc.4](sase-1bc.4.md) | 2026-09-27 13:29:47 EDT |
