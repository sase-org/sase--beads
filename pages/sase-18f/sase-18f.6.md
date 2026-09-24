# Bead: sase-18f.6 — Refuse closing a flag bead while its registry definition survives

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.6` · **Size:** small
**Created:** 2026-09-24 17:19:00 EDT · **Closed:** 2026-09-24 18:13:36 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

flag-close-guard: mirror the leftover --epic-symbol refusal in `sase bead close`. Refuse to close a flag task bead while the working tree's feature-flag registry still defines a flag naming it, because check_feature_flags rule 7 would redden every workspace.

## Notes

[2026-09-24T22:13:36Z · sase-18f.6] Added raise_if_surviving_flag_definition (epic_symbols.py), called from CLI close and ACE TUI close; refuses closing a bead named by the working tree's flag registry. Unit test added; ruff/mypy clean, 522 bead tests pass. Full 'sase tool run check' failed in _setup (required-plugin install, environmental), so not run end-to-end.

## Dependencies

- **Blocks:** [sase-18f.9](sase-18f.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.6/README.md) | [sase-18f.6](sase-18f.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fdc3e3c`](https://github.com/sase-org/sase/commit/fdc3e3caf65d7d6a56ae0499dd11fac92efd8066) | feat(bead): refuse closing a flag bead while its registry definition survives | [sase-18f.6](sase-18f.6.md) | 2026-09-24 18:14:28 EDT |
