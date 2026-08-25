# Bead: sase-ti.3 — Repair run-written path attribution outside the primary repo

[Bead Pages](../README.md) / [sase-ti](README.md) / sase-ti.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d9](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d9.md) · **Assignee:** `sase-ti.3` · **Size:** small
**Created:** 2026-08-25 07:37:57 EDT · **Closed:** 2026-08-25 07:56:26 EDT
**Plan:** [202608/commit\_finalizer\_protection\_truth.md](https://github.com/sase-org/sase--plans/blob/main/202608/commit_finalizer_protection_truth.md)

## Description

attribution: stop discarding the absolute tool-call path before the only code that can relativize it against a repository root, so direct writes into linked, sidecar, and external repos are visible to both the declaration evidence and the deferral counter-evidence check.

## Notes

[2026-08-25T11:56:01Z · sase-ti.3] PROPOSED FOLLOW-UP: `just check` fails at fmt-py-check because src/sase/sdd/_store_link.py has an unformatted trailing-blank-line diff (introduced in 51f6369b3, unrelated to this phase). Run `ruff format src/sase/sdd/_store_link.py` to fix.

[2026-08-25T11:56:26Z · sase-ti.3] Fixed run-written path attribution outside the primary repo: written_paths_from_tool_calls() (src/sase/finalizers/declaration_recovery_evidence.py) no longer destroys the absolute tool-call path via _workspace_relative before matching; it now returns paths verbatim, with relativization applied only at human-readable render time. Added a shared direct_written_paths() helper (replacing the two near-identical _direct_written_paths copies in declaration_context_evidence.py and declaration_deferrals.py) that relativizes an absolute written path against the actual repository root, so a direct write into a linked/sidecar/external repo is now correctly attributed. Verified with a regression test replaying the run 20260825070100 scenario (write into a sdd sidecar via absolute path, asserting written_by_this_run=true and that a belongs_to_another_turn deferral for that path is rejected), plus a sibling-prefix-repo-root negative test proving the matcher isn't fooled by path-string prefixes. tests/test_finalizer_declaration_channel_context.py, tests/test_finalizer_declaration_channel_deferrals.py, and tests/test_finalizer_declaration_recovery_evidence.py all pass (28 tests); full finalizer suite (361 tests) passes; ruff check/format and mypy clean on all changed files. just check's fmt-py-check gate fails only on a pre-existing, unrelated file (src/sase/sdd/_store_link.py from commit 51f6369b3) — recorded as a PROPOSED FOLLOW-UP note on this bead.

## Dependencies

- **Blocks:** [sase-ti.6](sase-ti.6.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ti.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ti.3/README.md) | [sase-ti.3](sase-ti.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f67d6e6`](https://github.com/sase-org/sase/commit/f67d6e6a44a42afebab52ace729e8f1f22d11e92) | fix(finalizers): attribute run-written paths outside the primary repo | [sase-ti.3](sase-ti.3.md) | 2026-08-25 07:57:21 EDT |
