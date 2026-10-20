# Bead: sase-1nf.10.1.1 — Put failure accounting and bounded selection policy in Rust

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.1` · **Size:** medium
**Created:** 2026-10-20 15:40:51 EDT · **Closed:** 2026-10-20 17:17:49 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

## Description

retry-policy: extend publication recovery wire types, centralize error classes and attempt charging, and implement deterministic bounded request selection with binding tests.

## Notes

[2026-10-20T21:17:23Z · sase-1nf.10.1.1] PROPOSED FOLLOW-UP: KNOWN test_tui_app_import_stays_under_startup_budget — 3522 modules vs 3522 cap on sase tool run check d138f0298aefe5dbaec022365136f761 (witness 0565caed0d1ee997557a16ec01dc1ecb); unrelated to publication recovery facades

[2026-10-20T21:17:28Z · sase-1nf.10.1.1] PROPOSED FOLLOW-UP: FLAKY test_behavioral_modules_do_not_dispatch_on_ref_prefix — util/imported_revision.py extra offender on the same ToolRun; already tracked by sase-174

[2026-10-20T21:17:33Z · sase-1nf.10.1.1] PROPOSED FOLLOW-UP: FLAKY test_contract_manifest_matches_marker_selection — stale tests/contract_manifest.txt on full-lane just check d138f0298aefe5dbaec022365136f761; same flake noted on sase-1nf.7 / sase-1n8.3 (sase-1ng tracks the sibling contract-set budget node)

[2026-10-20T21:17:49Z · sase-1nf.10.1.1] retry-policy landed: Rust agent_publication_recovery now classifies publication errors, decides scoped failure accounting (repository/unknown never charge; hood uses attempt threshold + repeated-format-error retirement), extends select_publication_retries with optional limit and error_classes, and adds select_publication_drain (at most N, preferred key first, oldest-active then eligible stopped; empty never means drain everything). Thin Python facade + PyO3 bindings. Wire stays schema v1. sase-core check 63d7e08e523a6b701379593623ecc996 passed. sase check d138f0298aefe5dbaec022365136f761 verdict no_new_failures (1 KNOWN TUI import budget, 2 FLAKY already tracked). Unused facade APIs epic-symbol keyed to sase-1nf.10.1.3. Host should commit both repos and move the core pin.

## Dependencies

- **Blocks:** [sase-1nf.10.1.3](sase-1nf.10.1.3.md) ◐ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.7](sase-1nf.10.1.7.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.1/README.md) | [sase-1nf.10.1.1](sase-1nf.10.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f9aa563`](https://github.com/sase-org/sase-core/commit/f9aa563c114c1fb1a4ee6a22f6b893ee42ef756f) | feat(publication-recovery): add failure accounting and bounded drain selection | [sase-1nf.10.1.1](sase-1nf.10.1.1.md) | 2026-10-20 17:20:54 EDT |
