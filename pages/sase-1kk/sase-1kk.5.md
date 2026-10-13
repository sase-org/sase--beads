# Bead: sase-1kk.5 — Route Python artifact-index readers and alias writes through Rust

[Bead Pages](../README.md) / [sase-1kk](README.md) / sase-1kk.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.104](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.104.md) · **Assignee:** `sase-1kk.5` · **Size:** small
**Created:** 2026-10-13 12:24:29 EDT · **Closed:** 2026-10-13 15:16:37 EDT
**Plan:** [202610/tui\_sigbus\_single\_sqlite\_owner.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_sigbus_single_sqlite_owner.md)

## Description

py-index-readers: move the sase-core pin and switch the lifecycle schema check, catalog projection, chat provenance reader, and layout alias CLI to the new bindings.

## Notes

[2026-10-13T19:16:24Z · sase-1kk.5] PROPOSED FOLLOW-UP: TUI app import budget remains over cap (3519 modules vs 3513); reproduced identically on clean base HEAD 731b7b18b5, so this phase did not cause it. Existing owner: sase-1ic.

[2026-10-13T19:16:37Z · sase-1kk.5] Moved the core pin to d30e1337; routed schema version, catalog and provenance projections, and layout aliases through Rust bindings; removed Python SQLite access for these artifact-index sites. just check: 55,527 passed, 1 known import-budget failure; reproduced unchanged on clean base (3,519 vs 3,513) and recorded follow-up citing sase-1ic.

## Dependencies

- **Depends on:** [sase-1kk.1](sase-1kk.1.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1kk.3](sase-1kk.3.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1kk.6](sase-1kk.6.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kk.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kk.5/README.md) | [sase-1kk.5](sase-1kk.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`432dd1f`](https://github.com/sase-org/sase/commit/432dd1f75952cc1505b28a308d477192a4cf7a51) | feat(agent-index): route Python readers through Rust | [sase-1kk.5](sase-1kk.5.md) | 2026-10-13 15:17:50 EDT |
