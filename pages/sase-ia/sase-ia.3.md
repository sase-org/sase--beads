# Bead: sase-ia.3 — Nested reads with legacy fallback

[Bead Pages](../README.md) / [sase-ia](README.md) / sase-ia.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.we.f0.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.we.f0.w1/README.md) · **Assignee:** `sase-ia.3` · **Size:** medium
**Created:** 2026-08-09 10:23:37 EDT · **Closed:** 2026-08-09 11:02:43 EDT
**Plan:** [202608/memory\_config\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_config_section.md)

## Description

read-sites: add one shared glossary-location resolver, read `memory.h1_title` and `memory.glossary` first with a legacy fallback in the AMD title loader, the memory init glossary loader, and the editor glossary catalog, and update every affected test fixture.

## Notes

[2026-08-09T15:02:43Z · sase-ia.3] Implemented nested memory.glossary and memory.h1_title readers with legacy fallback; verified focused pytest suite, just check, and just check-full.

[2026-08-09T15:04:07Z · sase-ia.3] Verified focused pytest suite (68 passed), just check passed, and just check-full passed.

## Dependencies

- **Blocks:** [sase-ia.4](sase-ia.4.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-ia.5](sase-ia.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ia.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.3/README.md) | [sase-ia.3](sase-ia.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3ec0251`](https://github.com/sase-org/sase/commit/3ec02513e7da173b4a4d095e3d415861bf89230c) | feat(memory): read glossary settings from nested config | [sase-ia.3](sase-ia.3.md) | 2026-08-09 11:05:23 EDT |
