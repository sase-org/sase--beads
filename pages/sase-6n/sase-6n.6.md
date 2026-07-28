# Bead: sase-6n.6 — Three-level Agents-tab tree and clan runtime column

[Bead Pages](../README.md) / [sase-6n](README.md) / sase-6n.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6n.6`
**Created:** 2026-07-17 21:35:19 UTC
**Plan:** [202607/agent\_clans\_families\_tribes.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_clans_families_tribes.md)

## Description

'Phase tui-tree' section: add synthetic clan rows, clan-aware h/l fold levels with a third indentation level, the corrected wall-clock clan runtime column, and clan-aware kill/dismiss cascades.

## Notes

Implemented the three-level Agents-tab clan tree with synthetic clan rows, clan/member/family indentation and three-state h/l folding; clan status/tag/runtime projection using the Rust overlap-aware aggregate; clan kill/dismiss cascades and synthetic-row persistence guards; help/footer/cache/query/grouping integration; and collapsed/expanded/fully-expanded PNG coverage. Verification: just test passed (18,206 passed, 7 skipped); just lint and committed-plan validation passed. just check passed all repository-local format/lint/type/Symvision gates, then stopped at pre-existing generated sase_agents_status skill drift in five linked chezmoi provider copies.

## Dependencies

- **Depends on:** [sase-6n.1](sase-6n.1.md) ✓
- **Depends on:** [sase-6n.2](sase-6n.2.md) ✓
- **Blocks:** [sase-6n.7](sase-6n.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6n.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6n.6/README.md) | [sase-6n.6](sase-6n.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`21d995c`](https://github.com/sase-org/sase/commit/21d995ce59c5b684e06ee947288e95dd07bec0b8) | feat(ace): add clan hierarchy to agents tab (sase-6n.6) | [sase-6n.6](sase-6n.6.md) | 2026-07-17 23:41:18 |
