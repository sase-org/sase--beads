# Bead: sase-y3.1 — Make removed link indexes committable

[Bead Pages](../README.md) / [sase-y3](README.md) / sase-y3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04n.md) · **Assignee:** `sase-y3.1` · **Size:** small
**Created:** 2026-09-07 15:14:45 EDT · **Closed:** 2026-09-07 15:39:40 EDT
**Plan:** [202609/machine\_link\_mutations\_off\_primary.md](https://github.com/sase-org/sase--plans/blob/main/202609/machine_link_mutations_off_primary.md)

## Description

stage-removed-link-indexes: validate deleted per-artifact link-index paths by canonical location instead of on-disk content in _group_valid_indexes so rename repairs commit their deletions alongside their rewrites, with regression tests proving one clean commit and no leftover worktree dirt.

## Notes

[2026-09-07T19:39:40Z · sase-y3.1] Implemented location-based validation for deleted artifact link indexes; verified with .venv/bin/pytest tests/sdd/test_artifact_link_files.py tests/sdd/test_artifact_link_rename_repair.py -q, just install, just fmt, just check, and sase bead epic-symbols sase-y3.1 showed no entries.

## Dependencies

- **Blocks:** [sase-y3.2](sase-y3.2.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-y3.3](sase-y3.3.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y3.1/README.md) | [sase-y3.1](sase-y3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec6bc4a`](https://github.com/sase-org/sase/commit/ec6bc4a422f56b8fa45dc809f26cc8f6ea7c3e33) | fix(artifact-links): commit removed link indexes | [sase-y3.1](sase-y3.1.md) | 2026-09-07 15:41:02 EDT |
