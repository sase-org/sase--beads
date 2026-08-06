# Bead: sase-gi.1 — Shared list-marker model and the ordered renumber engine

[Bead Pages](../README.md) / [sase-gi](README.md) / sase-gi.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.1` · **Size:** medium
**Created:** 2026-08-06 15:22:38 EDT · **Closed:** 2026-08-06 16:11:41 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

core: add the pure marker/boundary/ownership primitives shared by both marker families, the ordered run scanner, the Prettier-compatible renumber engine, and the single-TextEdit list-edit planner; refactor the hyphen helpers onto the shared primitives with no behavior change.

## Notes

[2026-08-06T20:10:55Z · sase-gi.1] Numbering rule correction for later phases: the plan says repeat style is "second item equals the first"; Prettier actually detects its "git diff friendly" style from the SECOND item being numbered 1 (with a first==0 special case needing the third to be 1 too), and then keeps item 0 at its own number while every later item stays 1. OrderedRun.repeat_style/number_at implement Prettier's real rule (verified against the prettier binary in tests/ace/tui/widgets/test_prompt_ordered_formatter_agreement.py), per design principle 2 (live numbering agrees with the formatter). Phases 2-5 should use OrderedRun.number_at / prompt_ordered_sibling_prefix rather than reimplementing the plan text.

[2026-08-06T20:11:13Z · sase-gi.1] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is load-flaky — it failed once during a just check run under heavy machine contention (load ~38, pytest -n 6) and passed in isolation and on a clean re-run; the timing budget should tolerate contention.

[2026-08-06T20:11:22Z · sase-gi.1] PROPOSED FOLLOW-UP: symvision epic-symbol whitelist entries for sase-gi.2/.4/.5 were added to the Justfile _lint-symvision recipe for the pure-layer symbols this phase introduces (is_prompt_ordered_marker_only, is_prompt_ordered_content_column, prompt_ordered_row_has_item_above, prompt_ordered_sibling_prefix, plan_ordered_list_edit, OrderedRun, RenumberResult, find_ordered_run, renumber_ordered_runs, strip_prompt_ordered_marker) — each entry must be removed as its consuming phase lands.

[2026-08-06T20:11:41Z · sase-gi.1] Added _prompt_list_markers.py (MarkerFamily, ListMarker with row/indent/number/digits/delimiter/content-column, family-scoped marker matching, boundary detection, bounded ownership scan, owned_block_end) and _prompt_ordered_editing.py (ordered marker predicates + strip, run scanner across blank lines/owned continuations/nested runs/delimiter scope, Prettier style detection, inserted-number rule, renumber pass with owned-block width shifting and cursor-column tracking, and plan_ordered_list_edit: apply-copy -> renumber -> minimal-row diff -> one TextEdit, with silent cap degradation at 400 items / 2000 scanned lines). Refactored _prompt_bullet_editing.py onto the shared primitives with no behavior change: all 177 existing tests in test_prompt_bullet_*.py and test_prompt_normal_mode_join.py pass unchanged and ordered markers remain hyphen boundaries. New tests: test_prompt_ordered_list_helpers.py, test_prompt_ordered_renumber.py, and test_prompt_ordered_formatter_agreement.py (real-prettier agreement in both directions, skipped when prettier is unavailable/disabled). Verified with just install + just check: every lint gate green (including symvision with new --epic-symbol entries for phases .2/.4/.5) and the test lane escalated to the full suite by the Justfile change and passed.

[2026-08-06T20:12:40Z · sase-gi.1] just install + just check green: all lint gates (ruff, mypy, keep-sorted, symvision, toobig, changelog, pyscripts, formatting, SASE validation) plus the escalated full test suite; 177 pre-existing hyphen/join tests unchanged, 145 new ordered-list tests pass including prettier-binary formatter-agreement tests.

## Dependencies

- **Blocks:** [sase-gi.2](sase-gi.2.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.4](sase-gi.4.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.6](sase-gi.6.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.1/README.md) | [sase-gi.1](sase-gi.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cb1007e`](https://github.com/sase-org/sase/commit/cb1007e0900c4be02fe4b94d966ccbec164a503d) | feat(ace-tui): add shared list-marker model and ordered renumber engine | [sase-gi.1](sase-gi.1.md) | 2026-08-06 16:13:57 EDT |
