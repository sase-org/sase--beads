# Bead: sase-1au.6.1 — Fail closed when the Prompts lifecycle snapshot cannot be read

[Bead Pages](../README.md) / [sase-1au.6](sase-1au.6.md) / sase-1au.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1au.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1au.land.md) · **Assignee:** `sase-1au.6.1` · **Size:** medium
**Created:** 2026-09-26 20:02:01 EDT · **Closed:** 2026-09-26 20:21:19 EDT
**Plan:** [202609/prompts\_overlay\_cutover\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompts_overlay_cutover_remainder.md)

## Description

fail_closed_read: remove the active-only fallback and cover stale bindings and failed lifecycle reads without hiding Trash.

## Notes

[2026-09-27T00:21:01Z · sase-1au.6.1--1] PROPOSED FOLLOW-UP: just check mypy fails on clean base tree identically (8 errors in _tree.py:622-629 and _node_finder_snapshot.py:617-667, byte-identical via targeted mypy on stashed base); unrelated to fail_closed_read, no owner per triage

[2026-09-27T00:21:19Z · sase-1au.6.1--1] fail_closed_read done: lifecycle read authoritative (no active-only fallback), stale/store/lock failures surface truthful error with no overlay; 27/27 targeted tests pass (fail_closed_read, restore_open, history_requests); changed files mypy+ruff clean; just check mypy 8 errors reproduce byte-identically on clean base (pre-existing, noted as follow-up)

## Dependencies

- **Blocks:** [sase-1au.6.3](sase-1au.6.3.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1au.6.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1au.6.1.md) | [sase-1au.6.1](sase-1au.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7e54203`](https://github.com/sase-org/sase/commit/7e54203ba044ae262ffea9ca4670a6a2bb898a3c) | fix(ace-tui): make prompt-bar stash restore fail-closed on snapshot read | [sase-1au.6.1](sase-1au.6.1.md) | 2026-09-26 20:23:36 EDT |
