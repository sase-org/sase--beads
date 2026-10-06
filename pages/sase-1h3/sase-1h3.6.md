# Bead: sase-1h3.6 — Scoreboard manifest coverage and intended-vs-observed section diff

[Bead Pages](../README.md) / [sase-1h3](README.md) / sase-1h3.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xc.md) · **Assignee:** `sase-1h3.6` · **Size:** medium
**Created:** 2026-10-06 12:43:32 EDT · **Closed:** 2026-10-06 17:15:30 EDT
**Plan:** [202610/e2\_instruction\_bundles\_shadow\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_instruction_bundles_shadow_mode.md)

## Description

scoreboard: add the manifest coverage column, the coverage view, the per-section intended-vs-observed diff, and the instructions.coverage doctor check, leaving every E1 column unchanged.

## Notes

[2026-10-06T21:14:50Z · sase-1h3.6] PROPOSED FOLLOW-UP: symvision gate fails identically on the clean base tree (private _runs imports in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py); unrelated to scoreboard work

[2026-10-06T21:15:10Z · sase-1h3.6] PROPOSED FOLLOW-UP: two tests/completion candidate tests (project providers empty-store, resource plan refs) fail identically on the clean base tree; unrelated to scoreboard work

[2026-10-06T21:15:30Z · sase-1h3.6] Scoreboard phase done: manifest k/N column, verify -c coverage table with errors and warm/cold render_ms p50/p95, -a intended-vs-observed section diff (native/explicit channels, frame/heading-only skipped), additive JSON (per-row coverage, top-level coverage block, per-observation section_diff, schema 1), instructions.coverage doctor check. Verified: 98 passed in tests/instructions, live verify -c and doctor -D -C instructions run, fmt/ruff/mypy/validate and remaining lint gates pass. Two base-identical failures recorded as follow-ups (symvision _runs imports, 2 completion candidate tests).

## Dependencies

- **Depends on:** [sase-1h3.5](sase-1h3.5.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h3.7](sase-1h3.7.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h3.6/README.md) | [sase-1h3.6](sase-1h3.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`66d598d`](https://github.com/sase-org/sase/commit/66d598d1987bdee617cb01e8abe3664dbc0a911d) | feat(instructions): add scoreboard coverage, verify diff and doctor check | [sase-1h3.6](sase-1h3.6.md) | 2026-10-06 17:24:45 EDT |
