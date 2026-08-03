# Bead: sase-en.4 — End-to-end budget guard and documentation

[Bead Pages](../README.md) / [sase-en](README.md) / sase-en.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sl.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sl.f1/README.md) · **Assignee:** `sase-en.4` · **Size:** small
**Created:** 2026-08-03 08:40:45 EDT · **Closed:** 2026-08-03 10:11:03 EDT
**Plan:** [202608/bead\_show\_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)

## Description

guard: assert the combined end-to-end cost ceiling and the output-identity invariant across formats, then record the new performance characteristics in the changelog and bead docs.

## Notes

[2026-08-03T14:11:03Z · sase-en.4] Added tests/test_bead/test_cli_show_budget.py (single-pass detail read == exactly 1 call, ref-bearing bead's repo-inventory subprocess probes bounded at 1-2) and extended tests/test_bead/test_cli_show_style.py with --format compact and --format json style-invariant coverage across the full 9-entry corpus (parser_ace/parser_vcs absence and subprocess-count-via-bead-show are already asserted end-to-end in tests/main/test_parser_narrowing.py from the parser phase). No golden bytes changed. Documented the single-store-read/narrow-parser/memoized-inventory combination in docs/beads.md. Verified ruff, mypy, changelog lint, toobig, sase validate, and validate-committed-plans all pass; tests/test_bead, tests/main, tests/test_repo_inventory*, tests/test_linked_repo* all green except 5 pre-existing failures (test_cli_changespec, test_cli_golden[init], test_cli_resolution x2, test_bead_fast_path_context) confirmed via git stash to reproduce identically on clean master, unrelated to this change. Measured in this sandbox with hyperfine -w3 -m10: sase bead show sase-bv 791ms (was 1.841s, 2.33x), sase bead show sase-cl 1.539s (was 3.184s, 2.07x) -- absolute ms exceed the modeled ~364/600ms budget due to this sandbox's slower subprocess/IO overhead, but the epic's guard is structural (call counts, module absence), not wall-clock, so this doesn't threaten the invariant. CHANGELOG.md is release-please-managed (validated by tools/validate_changelog) so the before/after numbers went into the commit message instead of a hand edit.

[2026-08-03T14:11:14Z · sase-en.4] PROPOSED FOLLOW-UP: 5 pre-existing test failures reproduce on clean master in this sandbox workspace -- tests/test_bead/test_cli_changespec.py::test_create_plan_stores_sibling_workspace_plan_path_relative_to_primary, tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[init], tests/test_bead/test_cli_resolution.py::test_workspace_context_rejects_primary_outside_pytest_sandbox and ::test_plain_checkout_non_sidecar_record_falls_back_to_legacy_resolution, tests/main/test_bead_fast_path_context.py::test_lightweight_context_uses_primary_vc_store_over_primary_non_vc_in_vc_mode -- all appear to assume a pytest tmp_path layout that this sandbox environment does not provide (assertions about resolved paths under /tmp mismatch actual pytest-of-<user> subdirs). Worth a task bead to make these tests environment-agnostic or skip cleanly when the assumption does not hold.

## Dependencies

- **Depends on:** [sase-en.1](sase-en.1.md) ✓
- **Depends on:** [sase-en.2](sase-en.2.md) ✓
- **Depends on:** [sase-en.3](sase-en.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-en.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-en.4/README.md) | [sase-en.4](sase-en.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18d438b`](https://github.com/sase-org/sase/commit/18d438bc066a15569c2f2faa393ffa4e1aa94f11) | test(bead): guard the show speedup's end-to-end budget | [sase-en.4](sase-en.4.md) | 2026-08-03 10:11:46 EDT |
