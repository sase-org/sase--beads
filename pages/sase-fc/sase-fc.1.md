# Bead: sase-fc.1 — Shared bead time presentation module

[Bead Pages](../README.md) / [sase-fc](README.md) / sase-fc.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.1` · **Size:** medium
**Created:** 2026-08-05 16:28:32 EDT · **Closed:** 2026-08-05 16:48:29 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

presentation: add src/sase/bead_time_presentation.py as the single source of bead instant and age rendering (glyphs, teal accent, absolute labels, compact age labels, Rich chips, ANSI CLI cells), with honest placeholders for unparseable values and a patchable clock indirection, plus unit tests.

## Notes

[2026-08-05T20:48:16Z · sase-fc.1] PROPOSED FOLLOW-UP: wire_pages phase must reconcile the unparseable-value branch — bead_pages._render_instant returns md_escape(value) while bead_instant_label returns "unknown", so a blind delegation changes page bytes for any bead with a malformed created_at.

[2026-08-05T20:48:29Z · sase-fc.1] Added src/sase/bead_time_presentation.py (glyphs ⧖/✎, #5FAFAF accent, Rich + ANSI styles, bead_instant_label/bead_age_label/bead_created_label/bead_created_chip/bead_updated_chip/bead_created_cli/suppress_duplicate_updated) with lazy sase.core.time module-attribute clock access so test local_now pins reach it; added tests/test_bead_time_presentation.py (44 cases: Z/naive/epoch shapes, every age bucket boundary, future-clamp, honest 'unknown'/empty placeholders, relative=False, dedupe predicate) and 7 --epic-symbol entries in the Justfile. No callers changed. just check passes green (fmt, ruff, mypy, symvision, toobig, tests).

## Dependencies

- **Blocks:** [sase-fc.2](sase-fc.2.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.3](sase-fc.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.4](sase-fc.4.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.5](sase-fc.5.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.6](sase-fc.6.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fc.7](sase-fc.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.1/README.md) | [sase-fc.1](sase-fc.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`53fc8d9`](https://github.com/sase-org/sase/commit/53fc8d9f89160af121517827803d134f41102252) | feat(bead): add shared bead time presentation module | [sase-fc.1](sase-fc.1.md) | 2026-08-05 16:49:19 EDT |
