# Bead: sase-1i5.5 — TUI macro-arg detection uses sase-core structural spans (sase-1h1)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.5` · **Size:** medium
**Created:** 2026-10-08 09:47:20 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

macro-arg-spans: replace raw comma and paren splitting in the TUI macro-arg detector with sase-core argument spans, add quoted-comma and quoted-paren golden fixtures in both repos, and close sase-1h1.

## Notes

[2026-10-08T14:46:24Z · sase-1i5.5] PROPOSED FOLLOW-UP: Python colon parser ignores quoted values — sase.macro._parsing parses #m:"a,b",staging as arg-less (ref end=2), so the choice-projection parity harness cannot re-bind colon-quoted applied edits; quoted-comma golden case ships without applied_edits

[2026-10-08T14:46:34Z · sase-1i5.5] PROPOSED FOLLOW-UP: TUI import budget still over cap on clean base (3582 vs 3570, identical with and without this phase) — owned by sase-13p via phase sase-1i5.8; this phase adds no eager imports

## Dependencies

- **Blocks:** [sase-1i5.8](sase-1i5.8.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.5.md) | [sase-1i5.5](sase-1i5.5.md) | 0 |
