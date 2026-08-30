# Bead: sase-vw.2 — Link scanner and target resolver

[Bead Pages](../README.md) / [sase-vw](README.md) / sase-vw.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.2` · **Size:** medium
**Created:** 2026-08-30 10:02:16 EDT · **Closed:** 2026-08-30 10:45:36 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

## Description

scan: add the `[[target]]` / `![[target]]` body scanner that skips code zones, plus a resolver that maps a raw target onto a flat note, web descriptor, or strand.

## Notes

[2026-08-30T14:45:36Z · sase-vw.2] Implemented the memory link scanner/resolver modules with focused tests. Verified: uv run pytest tests/memory/test_memory_links.py; just _lint-symvision; just check (64 scoped test files selected); sase bead epic-symbols sase-vw.2 reported no entries.

## Dependencies

- **Blocks:** [sase-vw.3](sase-vw.3.md) ◐ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.2/README.md) | [sase-vw.2](sase-vw.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae83faa`](https://github.com/sase-org/sase/commit/ae83faa2e020c5b9966badd44a0758b4cb271331) | feat(memory): add authored link scanner and resolver | [sase-vw.2](sase-vw.2.md) | 2026-08-30 10:47:13 EDT |
