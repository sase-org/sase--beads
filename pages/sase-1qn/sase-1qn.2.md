# Bead: sase-1qn.2 — Stop behavior-neutral module splits from turning the TUI import budget red (sase-1ic)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.2` · **Size:** large
**Created:** 2026-11-01 14:34:48 EST · **Closed:** 2026-11-01 17:32:01 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

import-budget-churn: the first-party TUI import-count guard in tests/ace/tui/test_app_import_budget.py has been re-raised after toobig splits and reopened twice (+35). Make the guard catch genuine new import-path work while staying neutral to mechanical splits of modules already on the path, without weakening the deferred-module list or just raising the cap again. Verify against recent split commits and a synthetic new eager import.

## Notes

[2026-11-01T19:47:14Z · sase-1qn.2] PLANNING EVIDENCE: No prior phase work notes; clean base 078e3da1d6. Existing import-budget tests pass 5/5 at 2860 first-party modules against strict 2861, but historical d3d26a5b55 reproduces the exact 2863-vs-2861 AssertionError. Same-interpreter split replays: eef22a0124 adds 3 modules and bffbc8effd adds 5. Prototype normalized source-token bytes across changed source files grow only 288 and 59 respectively (prompt staging split 362fcb2e7f: 69). Authored and validated a medium tale replacing tight module counting with a shared normalized-source-footprint guard while retaining deferred modules, CPU, and loose total limits. No implementation changes made; phase remains in progress for the plan handoff. No epic-symbol entries found.

[2026-11-01T22:31:38Z · sase-1qn.2] IMPLEMENTATION + MEASUREMENTS (clean base 078e3da1d6, Python 3.14.7, metric v1):
- tools/_tui_import_footprint.py (new, typed, added to typecheck_extensionless_tools) is the single probe+metric shared by tools/tui_import_closure and tests/ace/tui/test_app_import_budget.py. Footprint = UTF-8 bytes of significant tokens of the unique source files behind imported sase.* modules; ast picks excluded spans (imports, real docstrings, literal-string __all__ list/tuple assignments), tokenize measures original source. Source paths come from the modules the fresh interpreter actually imported; reading/parsing happens in the caller after counts, sys.modules and deferred results are captured, so measuring never inflates module counts or the import stopwatch.
- Cap: baseline 12,158,388 B + 4,096 allowance = 12,162,484, strict <. Kept: deferred-module list (identical), _MAX_TOTAL_MODULE_COUNT = 3904, 5.0s CPU / two-attempt policy. Module counts are diagnostics only; the old 2861 module cap is gone.
- Replays under the SAME cap (isolated git-archive snapshots in this workspace, same venv deps, removed afterwards): eef22a0124^ -> eef22a0124: 2860 -> 2863 modules, 12,160,347 -> 12,160,635 B (+288). bffbc8effd^ -> bffbc8effd: 2855 -> 2860, 12,153,966 -> 12,154,025 (+59). 362fcb2e7f^ -> 362fcb2e7f: 2856 -> 2860, 12,138,357 -> 12,138,426 (+69). d3d26a5b55 (reported failing tree): 2863 modules, 12,160,635 B, 1,849 under the cap. The deltas match the plan's prototype exactly. The OLD test run in an isolated d3d26a5b55 snapshot reproduced `assert 2863 < 2861`.
- tools/tui_import_closure now prints footprint, signed footprint change, per-source contributors (including changed contents of modules present on both sides; a net-zero split says 'footprint unchanged overall; source moved across N modules'), and keeps added/removed modules. No new CLI option.
- Tests: tests/ace/tui/test_app_import_budget.py (11), tests/test_tui_import_footprint.py (20, new), tests/test_tui_import_closure.py (11), shared real temp-package fixtures in tests/_tui_import_fixtures.py. Real fresh-subprocess proofs: facade+helpers split (repeated import/docstring boilerplate) keeps identical footprint and passes a cap with zero headroom; a new eager unrelated module trips an unchanged fixture cap; growth > 4,096 B trips the production allowance; small growth stays inside it; a previously deferred module fails independent of size and the message names it; third-party growth stays outside; strict equality fails; unicode/semicolon/alias/namespace/.pyc/missing-source/f-string brace cases covered.
- Overhead (separate from app import CPU of ~2.2s): footprint parse of the 2,860 sources is ~9s cold on a calm host (10-20s under load), 0.18s warm. A content-hash cache (in memory for tools; pytest cache dir for the real-app test, salted by helper source + interpreter) makes --diff parse only differing files and warm test runs ~7s.
- Docs: only the 'TUI import-budget ratchet' section of docs/contribute/perf-runbook.md was rewritten. No memory edits.
- Verification: just fix; sase tool run check 956013dd7868f03dca4572ee25b5562b succeeded (every stage, 583s) on the implementation. A rerun after a comment/wording-only tweak (a0017ac0a6d4fa79092b7070e0cd8c16) escalated to the full suite (core-identity-changed): 59,683 passed, 2 failed, both KNOWN and unrelated (see PROPOSED FOLLOW-UP). 45 focused tests pass.
- Limitation: the 4,096 B allowance admits small code growth by design. Real feature work is ~800 B per commit on average (tools/tui_import_closure --diff HEAD~12 shows +9,553 B across 12 commits, e.g. sase.monitor.settlement +4,464), so attributed cap raises per the test-comment policy should be expected; deferred-module exclusion stays absolute.

[2026-11-01T22:31:43Z · sase-1qn.2] TASK RESOLVED: sase-1ic — the TUI import guard now enforces a strict-< normalized source-footprint cap (12,158,388 B baseline at 078e3da1d6 + 4,096 = 12,162,484) instead of a first-party module count. Replays of eef22a0124, bffbc8effd and 362fcb2e7f (+288/+59/+69 B for +3/+5/+4 modules) and d3d26a5b55 (2,863 modules, 12,160,635 B) all pass the same cap unedited; real-subprocess fixtures prove a mechanical split is neutral while a new eager source import (and a >4,096 B one) and a previously deferred module still fail; deferred list, 3904 total cap and 5.0s CPU policy unchanged; sase tool run check 956013dd... succeeded.

[2026-11-01T22:31:49Z · sase-1qn.2] PROPOSED FOLLOW-UP: tests/test_pending_actions.py::test_transport_adapter_preserves_handled_state_and_original_lifecycle (KeyError 'abcd1234') and tests/test_stranded_work_facade.py::test_reduce_stranded_work_round_trips_through_real_binding (StrandedWorkReport schema_version 2, expected 1) fail identically on the clean base 078e3da1d6 (reproduced with this phase's changes stashed) against the installed sase_core_rs 0.43.3 binding built from the ahead sase-core checkout (check run a0017ac0a6d4fa79092b7070e0cd8c16, triage KNOWN) — pending-action and stranded-work wire/binding revision drift, unrelated to the import budget.

[2026-11-01T22:32:01Z · sase-1qn.2] Verified: strict-< normalized footprint cap 12,162,484 (baseline 12,158,388 + 4,096); replays of eef22a0124, bffbc8effd, 362fcb2e7f and d3d26a5b55 pass unchanged; real-subprocess fixtures prove split neutrality, eager-import and deferred-module failures; deferred list, total cap and CPU policy unchanged; just fix + sase tool run check 956013dd... succeeded (rerun's only failures were two KNOWN clean-base failures recorded as PROPOSED FOLLOW-UP).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.2.md) | [sase-1qn.2](sase-1qn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5d7a79c`](https://github.com/sase-org/sase/commit/5d7a79c3c01bb947078afc5fcabf7f21257cd6a7) | test(tui): measure the import budget in source footprint, not module count | [sase-1qn.2](sase-1qn.2.md) | 2026-11-01 17:33:29 EST |
