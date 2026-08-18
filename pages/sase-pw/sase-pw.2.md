# Bead: sase-pw.2 — Per-project accent colors

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.2` · **Size:** small
**Created:** 2026-08-18 11:30:32 EDT · **Closed:** 2026-08-18 11:51:26 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

palette: add `sase.ace.tui.project_styles` with a curated accent palette and a hash-plus-probe assignment that gives every enabled project a distinct, deterministic color.

## Notes

[2026-08-18T15:51:05Z · sase-pw.2] PROPOSED FOLLOW-UP: Justfile lines ~342-348 carry stale --epic-symbol "sase-pq.5(...)" entries (TaskTypeGateDisplay, parse_task_type_gate_display, resolve_task_type_gate_display, task_type_gate_chip, task_type_gate_display_payload, task_type_gate_markdown_fact, task_type_gate_note) for bead sase-pq.5, which is already closed. This breaks `just lint`/`just check` symvision gate for every agent repo-wide (confirmed pre-existing on master, unrelated to sase-pw.2). Needs the epic-symbol entries either resolved (annotate the still-live symbols or remove dead ones) or re-keyed to a still-open bead.

[2026-08-18T15:51:26Z · sase-pw.2] Added src/sase/ace/tui/project_styles.py with PROJECT_ACCENTS (18 OKLCH-hue-stepped, equal-relative-luminance hex colors matching _PROVIDER_ACCENTS legibility band), project_accent_map (sorted hash+forward-probe, memoized, degrades to repeats above 18 keys) and project_accent (single-key convenience, hash-only without among). Added tests/ace/tui/test_project_styles.py (7 tests: determinism, order-independence, all-distinct incl. a natural hash collision, stable-prefix on later insert, >18 degrade, hash-only vs among). Verified: pytest tests/ace/tui/test_project_styles.py -q (7 passed); ruff+mypy clean; just check green except the lint(symvision) gate, which fails only on pre-existing stale --epic-symbol entries for the unrelated, already-closed bead sase-pq.5 (confirmed present on master before this change) — logged as PROPOSED FOLLOW-UP on this bead. No --epic-symbol entries exist for sase-pw.2 itself.

[2026-08-18T15:52:05Z · sase-pw.2] Added src/sase/ace/tui/project_styles.py (PROJECT_ACCENTS 18-color OKLCH-stepped palette, project_accent_map(), project_accent()) and tests/ace/tui/test_project_styles.py (7 tests: determinism, order-independence, all-distinct incl. hash collision, stability on append, degrade-to-repeats past 18 keys, among/hash-only paths). Verified: new tests pass 7/7, ruff/mypy clean, just check green apart from lint(symvision) failing only on pre-existing stale --epic-symbol entries for unrelated already-closed bead sase-pq.5 (present on master before this change).

## Dependencies

- **Blocks:** [sase-pw.4](sase-pw.4.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.8](sase-pw.8.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pw.2/README.md) | [sase-pw.2](sase-pw.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`129bb63`](https://github.com/sase-org/sase/commit/129bb631d3725417e77b7d97ef8e184f52dbf339) | feat(tui): add per-project accent color palette | [sase-pw.2](sase-pw.2.md) | 2026-08-18 11:52:46 EDT |
