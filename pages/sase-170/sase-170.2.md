# Bead: sase-170.2 — Durable clan record store in sase-core

[Bead Pages](../README.md) / [sase-170](README.md) / sase-170.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pw.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pw.w0.md) · **Assignee:** `sase-170.2` · **Size:** medium
**Created:** 2026-09-23 11:39:54 EDT · **Closed:** 2026-09-23 12:16:52 EDT
**Plan:** [202609/tribe\_clan\_summaries\_and\_clan\_records.md](https://github.com/sase-org/sase--plans/blob/main/202609/tribe_clan_summaries_and_clan_records.md)

## Description

clan_record_core: in the linked sase-core repo, add the per-clan JSON record store (schema, merge rules, bounded locks, atomic writes, mtime cache), apply records over clan context in all three scan/index paths through a new clan_records_dir scan option, add capture-from-artifacts and launch-default resolution, and expose four Python bindings with tests.

## Notes

[2026-09-23T16:16:52Z · sase-170.2] clan_record_core done in sase-core: new agent_clan_record module (schema v1, merge rules, bounded locks, atomic writes, mtime cache, capture, launch defaults), clan_records_dir overlay in scan_agent_artifacts/scan_agent_artifact_dirs/query_agent_artifact_index, 4 Python bindings with round-trip tests; 15 core + index overlay + binding tests pass; sase tool run check succeeded

## Dependencies

- **Blocks:** [sase-170.3](sase-170.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-170.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.2/README.md) | [sase-170.2](sase-170.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7fc3501`](https://github.com/sase-org/sase-core/commit/7fc3501d49f28aff399e48bf0fe4f560523a8ab8) | feat(core): durable per-clan record store with scan overlay and bindings | [sase-170.2](sase-170.2.md) | 2026-09-23 12:18:33 EDT |
