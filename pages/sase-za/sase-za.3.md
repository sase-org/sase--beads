# Bead: sase-za.3 — Keep notifications.jsonl O(live)

[Bead Pages](../README.md) / [sase-za](README.md) / sase-za.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ih](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ih.md) · **Assignee:** `sase-za.3` · **Size:** medium
**Created:** 2026-09-10 11:44:18 EDT · **Closed:** 2026-09-10 12:40:36 EDT
**Plan:** [202609/host\_resource\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/host_resource_diet.md)

## Description

notification-compaction: add crash-safe automatic compaction with a retention window to the Rust notification store, archiving old dismissed rows to a sibling JSONL file with tests and unchanged Python caller behavior.

## Notes

[2026-09-10T16:39:57Z · sase-za.3] PROPOSED FOLLOW-UP: Ratchet sase-core-revision.txt after the finalizer-created sase-core commit lands - the pin tool targets remote HEAD and cannot point at this turn before that commit exists.

[2026-09-10T16:40:36Z · sase-za.3] Implemented automatic Rust notification compaction and verified cargo fmt; cargo test -p sase_core --test notification_store_parity; cargo test -p sase_core_py notification_store; PYO3_PYTHON=/home/bryan/.local/bin/python3.13 just check; rust-dev-install from linked core; and Python notification-store tests via the project venv.

## Dependencies

- **Blocks:** [sase-za.4](sase-za.4.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-za.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-za.3/README.md) | [sase-za.3](sase-za.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dc3d0a8`](https://github.com/sase-org/sase-core/commit/dc3d0a8b4e7e73538615c3e3aaec4c597a7252d3) | feat(notifications): compact old dismissed rows | [sase-za.3](sase-za.3.md) | 2026-09-10 12:42:00 EDT |
