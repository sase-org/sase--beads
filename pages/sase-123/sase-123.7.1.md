# Bead: sase-123.7.1 — Restore one renderer for screenshots and visual snapshots

[Bead Pages](../README.md) / [sase-123.7](sase-123.7.md) / sase-123.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-123.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-123.land.md) · **Assignee:** `sase-123.7.1` · **Size:** small
**Created:** 2026-09-17 21:13:50 EDT · **Closed:** 2026-09-17 22:19:07 EDT
**Plan:** [202609/complete\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_tui_screenshots.md)

## Description

canonical-renderer: remove the test-side rasterizer copy reintroduced by concurrent commits and repoint visual helpers and fingerprints to the packaged runtime renderer without changing pixels.

## Notes

[2026-09-18T02:01:04Z · sase-123.7.1] PROPOSED FOLLOW-UP: Gate decision tests are stale against Rust current-failure validation — `just check` escalated to the full non-visual suite and failed only `tests/test_gate_cli_show.py::test_show_reports_an_accepted_failed_gate` plus two `tests/test_gate_decision_acceptance.py` cases because their synthetic `attempt_failed` journal entries use an empty `attempt_id`, which `sase_core_rs 0.34.50` rejects as `execution_facts.current_failure.attempt_id must be nonempty`.

[2026-09-18T02:17:56Z · sase-123.7.1] PROPOSED FOLLOW-UP: Agents visual snapshot corpus has fresh drift unrelated to renderer consolidation — full `just test-visual` produced 107 Agents-family failures, but re-rendering `.pytest_cache/sase-visual/.../agents_list_120x40/actual.svg` with a verbatim copy of the removed test-local renderer produced identical bytes to `sase.ace.tui.visual_render.render_svg_to_png`; the runtime renderer output matched `actual.png` and differed from the committed golden.

[2026-09-18T02:19:07Z · sase-123.7.1] Removed the duplicated test-local SVG rasterizer/font discovery and repointed visual fixture facade, glyph audits, and renderer fingerprinting at packaged sase.ace.tui.visual_render. Verified focused renderer/glyph/fingerprint visual tests passed (273 passed), facade/font callers resolve to runtime renderer/fonts, old removed renderer and runtime renderer produce identical bytes for a failing Agents SVG, and built wheel contains DejaVuSans, FiraCode Bold/Regular, and NotoEmoji fonts. Ran just fix. just check escalated to the full non-visual suite and failed only three unrelated gate decision tests using empty attempt_id fixtures; full just test-visual failed 107 existing Agents-family golden mismatches unrelated to renderer bytes. Proposed follow-up notes recorded on this phase for both.

## Dependencies

- **Blocks:** [sase-123.7.5](sase-123.7.5.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-123.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-123.7.1/README.md) | [sase-123.7.1](sase-123.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d22e820`](https://github.com/sase-org/sase/commit/d22e8202157062623de6f7ce4930528bd3475521) | fix(tui): use canonical visual renderer | [sase-123.7.1](sase-123.7.1.md) | 2026-09-17 22:20:58 EDT |
