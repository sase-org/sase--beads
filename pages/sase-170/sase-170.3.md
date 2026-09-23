# Bead: sase-170.3 — Record, capture, and read clan attributes from sase

[Bead Pages](../README.md) / [sase-170](README.md) / sase-170.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pw.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pw.w0.md) · **Assignee:** `sase-170.3` · **Size:** medium
**Created:** 2026-09-23 11:39:55 EDT · **Closed:** 2026-09-23 13:42:28 EDT
**Plan:** [202609/tribe\_clan\_summaries\_and\_clan\_records.md](https://github.com/sase-org/sase--plans/blob/main/202609/tribe_clan_summaries_and_clan_records.md)

## Description

clan_record_wiring: bump the sase-core pin, add the Python facade, pass the records dir through every scan, record summaries and tribes at launch and on summary refresh, capture records before any artifact deletion, make the wait index honor recorded tribes, update docs, and add regression tests for the lost summary scenarios.

## Notes

[2026-09-23T17:41:47Z · sase-170.3] PROPOSED FOLLOW-UP: just check has 14 pre-existing failures on clean master (bead rendering x5 incl. edge case, bead cli_work_task x3, completion snapshot x2, link_trail, app_import_budget, query_profile_reference) plus 3 load-flaky tests (fakey monitor capacity e2e, prompt keymaps pane, load tiering oracle) — all fail without this phase diff; needs triage before epic sase-170 lands

[2026-09-23T17:42:28Z · sase-170.3] clan_record_wiring done: core pin cfe1902a (has clan_record_core), new agent_clan_record facade (4 bindings, strict flag), scan overlay via default clan_records_dir on every scan/index path, launch recording (declared/script/propagated) + refresh recording, capture-before-delete in try_delete and wipe, wait-index tribe overlay with tombstones and once-per-build cache, agent_families docs, 17 new tests in test_agent_clan_record_wiring.py all pass; symvision/ruff/mypy/fmt green; full just check: 45574 passed, 17 failed — all 17 verified unrelated (14 fail on clean master, 3 pass in isolation on this diff). Justfile gains --epic-symbol sase-170.5(resolve_clan_launch_defaults) for the launch-defaults phase.

## Dependencies

- **Depends on:** [sase-170.2](sase-170.2.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-170.4](sase-170.4.md) ◐ · ⧖ 2026-09-23
- **Blocks:** [sase-170.5](sase-170.5.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-170.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.3/README.md) | [sase-170.3](sase-170.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69a5ca5`](https://github.com/sase-org/sase/commit/69a5ca5e1d0d059f7a0c613526d6990629c045ae) | feat(clans): record, capture, and read clan attributes from sase | [sase-170.3](sase-170.3.md) | 2026-09-23 13:44:14 EDT |
