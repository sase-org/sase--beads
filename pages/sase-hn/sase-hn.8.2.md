# Bead: sase-hn.8.2 — Sweep the ACE surface

[Bead Pages](../README.md) / [sase-hn.8](sase-hn.8.md) / sase-hn.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.land/README.md) · **Assignee:** `sase-hn.8.2` · **Size:** large
**Created:** 2026-08-09 00:11:03 EDT · **Closed:** 2026-08-09 02:41:24 EDT
**Plan:** [202608/patch\_terminology\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_terminology_completion.md)

## Description

ace-surface: retire ChangeSpec vocabulary from ACE console output, toasts, TUI labels, docstrings, and canonical locals, including the glossary PNG snapshot fixture, while retained aliases and saved state keep working.

## Notes

[2026-08-09T06:41:24Z · sase-hn.8.2] Implemented approved ACE Patch/stitch terminology plan. Verified ACE terminology audit reports 0 src/sase/ace defects; targeted legacy-compatibility and TUI tests pass; full visual suite passed earlier (570 passed, 1 skipped); just install succeeded; just check passed, including lint, validation, and scoped test lane.

[2026-08-09T06:43:00Z · sase-hn.8.2] Implemented ACE Patch/stitch terminology migration; verified with just install, just check, full visual suite, and ACE terminology audit reporting 0 src/sase/ace defects.

## Dependencies

- **Depends on:** [sase-hn.8.1](sase-hn.8.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-hn.8.5](sase-hn.8.5.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hn.8.2.md) | [sase-hn.8.2](sase-hn.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`50f8961`](https://github.com/sase-org/sase/commit/50f8961ac7cb1b2ba654ed4bcb06804db433d42e) | feat(ace): rename ACE ChangeSpecs to Patches | [sase-hn.8.2](sase-hn.8.2.md) | 2026-08-09 02:48:05 EDT |
