# Bead: sase-ug.4 — A way to read durable truth and see the drift

[Bead Pages](../README.md) / [sase-ug](README.md) / sase-ug.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.4` · **Size:** medium
**Created:** 2026-08-26 14:48:26 EDT · **Closed:** 2026-08-26 20:31:08 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

## Description

truthread: give the CLI and doctor a durable-truth read path and a row-level drift report, and build the harness that tests any index against the store rather than against the aggregate.

## Notes

[2026-08-27T00:31:08Z · sase-ug.4] Implemented durable store reads for artifact link list, row-level aggregate drift reporting for artifact doctor and project doctor, projected-row drift coverage, and shared durable-index test harness. Verified with focused pytest, regenerated completion spec, ran just fmt, ran just check successfully, and confirmed sase bead epic-symbols sase-ug.4 has no entries.

## Dependencies

- **Depends on:** [sase-ug.1](sase-ug.1.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-ug.3](sase-ug.3.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ug.5](sase-ug.5.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ug.4/README.md) | [sase-ug.4](sase-ug.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`58e5a83`](https://github.com/sase-org/sase/commit/58e5a8310e26bd823209156c8890ee4fcb2ddfef) | feat(artifact-links): add durable truth drift reporting | [sase-ug.4](sase-ug.4.md) | 2026-08-26 20:32:42 EDT |
