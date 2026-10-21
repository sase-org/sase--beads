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

[2026-10-20T22:47:45Z · sase-1nf.10.1.1] PROPOSED FOLLOW-UP: allowlist git HEAD ref: parsing in imported_revision.py — tests/ace/tui/artifacts_contract/test_no_ref_prefix_dispatch.py::test_behavioral_modules_do_not_dispatch_on_ref_prefix fails NEW because src/sase/ace/tui/util/imported_revision.py uses startswith('ref:') / removeprefix('ref:') to parse .git/HEAD, not artifact pane ids. The file is already on master (aae7eae667) and is missing from the test allowlist. Fix: add TUI_ROOT / 'util' / 'imported_revision.py' to _ALLOWLIST with a git-HEAD comment, matching _memory_history_tokens.py. Independent of publication-recovery; surfaced during conflict-repair just check (sase tool run facb2b634a35bc423a89f88c84421084).

## Dependencies

- **Blocks:** [sase-1nf.10.1.3](sase-1nf.10.1.3.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.7](sase-1nf.10.1.7.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.1/README.md) | [sase-1nf.10.1.1](sase-1nf.10.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f9aa563`](https://github.com/sase-org/sase-core/commit/f9aa563c114c1fb1a4ee6a22f6b893ee42ef756f) | feat(publication-recovery): add failure accounting and bounded drain selection | [sase-1nf.10.1.1](sase-1nf.10.1.1.md) | 2026-10-20 17:20:54 EDT |
| sase | [`69dc952`](https://github.com/sase-org/sase/commit/69dc95277dd42d5758f6f122550e51916dc17acb) | feat(publication-recovery): facade for failure accounting and drain selection | [sase-1nf.10.1.1](sase-1nf.10.1.1.md) | 2026-10-20 18:41:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.1][1] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1nf.10.1.3][2] | Need prior phase work to consume Rust policy | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.3/README.md

<!-- sase:referenced-by:end -->
