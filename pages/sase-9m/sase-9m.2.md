# Bead: sase-9m.2 — Durable common-placeholder store and prompt recording hook

[Bead Pages](../README.md) / [sase-9m](README.md) / sase-9m.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9m.2` · **Size:** medium
**Created:** 2026-07-25 16:44:25 UTC
**Plan:** [202607/common\_placeholder\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202607/common_placeholder_tags.md)

## Description

'Phase store — durable common-placeholder store' section: add a capped, atomically-written JSON store of placeholder tags ranked by use count, record tags from every submitted or abandoned prompt through the shared prompt-history choke points, and seed the store once from existing prompt history.

## Notes

Added src/sase/history/prompt_placeholders.py: capped, atomically-written JSON store (version 1, sase_home()/prompt_placeholders.json) with LRU retention and count/last_used/text display ordering, a dedicated fcntl lock file, silent best-effort failure, and a bounded (24 newest shards) one-time seed from prompt history. Recording is hooked into add_or_update_prompt (before the is_recordable_prompt threshold, so short and cancelled prompts still contribute tags) and record_failed_launch_prompt via lazy imports. Tests: tests/history/test_prompt_placeholders.py (19 cases). Symvision epic-symbol entries added to the Justfile for the four public store APIs that phase wiring (sase-9m.3) will consume. Config field/default_config.yml/schema plumbing is intentionally left to phase wiring; the limit defaults to 100.

## Dependencies

- **Blocks:** [sase-9m.3](sase-9m.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9m.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9m.2/README.md) | [sase-9m.2](sase-9m.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9f8f04a`](https://github.com/sase-org/sase/commit/9f8f04a4ae7f927447469de0674ebb2ca76d38dd) | feat(history): add durable common-placeholder store (sase-9m.2) | [sase-9m.2](sase-9m.2.md) | 2026-07-25 17:11:27 |
