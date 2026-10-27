# Bead: sase-1ou.4 — Fix the Files ctrl+j page-anchor scroll race (sase-1a7)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.4` · **Size:** large
**Created:** 2026-10-27 09:20:59 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Description

deck-anchor: reproduce the intermittent wait_for_anchor_scroll timeout in test_files_ctrl_j_scrolls_page_anchor_to_top (it fails about 1 in 4 even in isolation), fix the Files spread scroll/anchor race in production code, prove it with isolated and loaded stress loops, and close sase-1a7.

## Dependencies

- **Depends on:** [sase-1ou.1](sase-1ou.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.4/README.md) | [sase-1ou.4](sase-1ou.4.md) | 0 |
