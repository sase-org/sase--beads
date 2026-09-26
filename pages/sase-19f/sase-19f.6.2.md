# Bead: sase-19f.6.2 — Render multiplier capacity and expose agent-list JSON

[Bead Pages](../README.md) / [sase-19f.6](sase-19f.6.md) / sase-19f.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-19f.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.land.md) · **Assignee:** `sase-19f.6.2` · **Size:** medium
**Created:** 2026-09-26 04:40:43 EDT · **Closed:** 2026-09-26 07:04:48 EDT
**Plan:** [202609/queue\_multiplier\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_multiplier_surfaces.md)

## Description

display-list: Render c1.5x badges, 1.5x budget and resolved units in the detail header, wait lane, queue ladder, and agent rows. Include the multiplier in display cache keys and runner-slot capacity models. Expose queue_capacity_multiplier in agent-list entries and JSON. Add focused widget and CLI/list tests.

## Notes

[2026-09-26T10:47:57Z · sase-19f.6.2] PROPOSED FOLLOW-UP: just lint symvision fails on four stale sase-1aa.3 epic-symbol entries (ModelManifest, ProviderRecord, manifest_provider_names, provider_model_supersedes); reproduces identically on clean base, owned by sase-1aa land agent

[2026-09-26T11:04:48Z · sase-19f.6.2] Display-list done: c1.5x badges + 1.5x budget (7.5 units) in rows, header, wait lane, queue ladder; multiplier in cache keys, capacity records, agent-list entries/JSON; consumed sase-19f(resolve_queue_capacity_multiplier) epic-symbol. Verified: 12 new focused tests pass, 222 neighboring + 856 models + 35 fleet/entry tests pass, all lint gates green except 4 pre-existing sase-1aa.3 symvision staleness errors proven identical on clean base (filed as PROPOSED FOLLOW-UP); full test-scoped exceeded the single-turn time limit.

## Dependencies

- **Depends on:** [sase-19f.6.1](sase-19f.6.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-19f.6.3](sase-19f.6.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19f.6.2/README.md) | [sase-19f.6.2](sase-19f.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5f676a2`](https://github.com/sase-org/sase/commit/5f676a28e8b3b3c9a7f3378200e448b60b75f9cd) | feat(ace-tui): render queue capacity multiplier end to end | [sase-19f.6.2](sase-19f.6.2.md) | 2026-09-26 07:07:11 EDT |
