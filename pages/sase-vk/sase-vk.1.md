# Bead: sase-vk.1 — Web descriptors stop declaring a rendering tier

[Bead Pages](../README.md) / [sase-vk](README.md) / sase-vk.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0g6.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0g6.w0.md) · **Assignee:** `sase-vk.1` · **Size:** medium
**Created:** 2026-08-29 11:29:34 EDT · **Closed:** 2026-08-29 12:33:17 EDT
**Plan:** [202608/memory\_webs\_agents\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs_agents_section.md)

## Description

webkind: delete MemoryWeb.rendering_type, stop reading type:/parent: from web descriptors, strip both keys on init, always inline every web descriptor, and update every consumer surface that displayed a web's rendering tier.

## Notes

[2026-08-29T16:33:17Z · sase-vk.1] Verified .venv/bin/sase memory init --check; descriptor flat reads are refused while keyed glossary strand reads work; focused README/memory/TUI pytest suite passed (158 passed); just test-visual passed (842 passed, 1 skipped); just check passed.

## Dependencies

- **Blocks:** [sase-vk.2](sase-vk.2.md) ◐ · ⧖ 2026-08-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vk.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vk.1/README.md) | [sase-vk.1](sase-vk.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1be5429`](https://github.com/sase-org/sase/commit/1be5429ea9812ff722c94cd2f1103ffc9b6142da) | feat(memory): make web descriptors tier-free | [sase-vk.1](sase-vk.1.md) | 2026-08-29 12:34:50 EDT |
