# Bead: sase-uv.7 — Project the heavy record\_json leaves off the list-render path

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.7` · **Size:** large
**Created:** 2026-08-27 12:26:47 EDT · **Closed:** 2026-08-27 16:19:23 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

projection: add a list-shaped record projection in sase-core that omits the four leaf fields making up 78% of the payload, and hydrate them lazily for the selected row.

## Notes

[2026-08-27T20:13:58Z · sase-uv.7] MEASUREMENT: Implementing-host projection measurement for plan:202608/projection_record_json_list_shape.md on 2026-08-27, against /home/bryan/.sase/agent_artifact_index.sqlite with the Tier 1 TUI-shaped query (include_active=1000, include_recent_completed=200, include_hidden=false, cached freshness): full/list records both 805; compact JSON payload full=12354992 bytes, list=6511354 bytes, saved=5843638 bytes (47.30%). Median raw PyO3 query call for the list shape, including SQL/decode plus serialize_to_py, was 569.49 ms over 7 samples; Python wire rehydration median was 152.91 ms. Warm load_tiered_agents comparison with patch_snapshot=[] and artifact_index Tier 1: forced full-shape samples [998.74, 1026.69, 944.60, 881.04, 792.34] ms, median 944.60 ms; default list-shape samples [777.50, 670.54, 635.80, 634.64, 701.85] ms, median 670.54 ms. refresh_stale_rows was verified by regression test to avoid selecting record_json; the abandoned repair scan now uses indexed done_outcome instead of record_json LIKE.

[2026-08-27T20:14:25Z · sase-uv.7] PROPOSED FOLLOW-UP: split heavy record details out of record_json — add a record_detail_json-style column or equivalent detail table so the index read and serde decode can also skip _raw/_data and linked-repo detail bytes, not just the GIL-held PyO3 serialization and Python rehydration work. This was intentionally out of scope for projection_record_json_list_shape.md because it needs a full-table migration and touches every record_json reader.

[2026-08-27T20:14:49Z · sase-uv.7] PROPOSED FOLLOW-UP: ratchet the pinned Rust core revision before landing — this phase added the load_agent_artifact_records PyO3 binding and the local core-floor probe reports it has no containing release tag yet, so CI's pinned-core binding gate will fail until sase-core-revision.txt is moved past the core commit and the published window sequencing is handled by the release flow.

[2026-08-27T20:19:23Z · sase-uv.7] Auto-closed by `sase stitch create` after create_commit landed a615273b1 ("feat(tui): hydrate list-shaped artifact records"). No verification is implied by this note. Reopen with `sase bead open sase-uv.7`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-uv.6](sase-uv.6.md) ✓ · ⧖ 2026-08-27
- **Blocks:** [sase-uv.8](sase-uv.8.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-uv.7.md) | [sase-uv.7](sase-uv.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a615273`](https://github.com/sase-org/sase/commit/a615273b13a5e0615ddbbc6a6c3747c58c19f8f8) | feat(tui): hydrate list-shaped artifact records | [sase-uv.7](sase-uv.7.md) | 2026-08-27 16:16:41 EDT |
| sase-core | [`sase-core@bdce575`](https://github.com/sase-org/sase-core/commit/bdce575a5bea16a97f0f5fd31947d42a7de81dd1) | feat(agent-scan): project list-shaped artifact records | [sase-uv.7](sase-uv.7.md) | 2026-08-27 16:19:51 EDT |
