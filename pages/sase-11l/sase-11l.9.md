# Bead: sase-11l.9 — Hood selector for %wait

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.9` · **Size:** medium
**Created:** 2026-09-15 22:46:06 EDT · **Closed:** 2026-09-18 10:03:25 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

wait-hood: give %wait a hood= keyword using the existing hood matcher, with contract, wait-resolution, completion, and parity-test updates.

## Notes

[2026-09-18T14:03:25Z · sase-11l.9] Implemented hood= waits; verified targeted Python wait/plan/TUI suites, cargo test -p sase_core, just check, and epic-symbols returned no entries.

## Dependencies

- **Blocks:** [sase-11l.10](sase-11l.10.md) ◐ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.6](sase-11l.6.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.9/README.md) | [sase-11l.9](sase-11l.9.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c8c842f`](https://github.com/sase-org/sase/commit/c8c842fb3e8f7e042e4e1543341f2be95ee77169) | feat(wait): support hood selectors | [sase-11l.9](sase-11l.9.md) | 2026-09-18 10:05:11 EDT |
| sase-core | [`sase-core@549b168`](https://github.com/sase-org/sase-core/commit/549b168603d0700cdee71d068905dc70987cf7c3) | feat(wait): add hood directive contract | [sase-11l.9](sase-11l.9.md) | 2026-09-18 10:09:02 EDT |
