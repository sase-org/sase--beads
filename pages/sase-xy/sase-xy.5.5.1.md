# Bead: sase-xy.5.5.1 — Finish repository-owned target selection in Rust core

[Bead Pages](../README.md) / [sase-xy.5.5](sase-xy.5.5.md) / sase-xy.5.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xy.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.5.land.md) · **Assignee:** `sase-xy.5.5.1` · **Size:** medium
**Created:** 2026-09-07 20:23:10 EDT · **Closed:** 2026-09-07 21:18:33 EDT
**Plan:** [202609/pager\_target\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_target_landing_repairs.md)

## Description

repository-target-contract: make source-directory, checkout identity, revision, filtering, directory, fallback, ambiguity, and bounded-search outcomes truthful in the shared Rust resolver.

## Notes

[2026-09-08T01:17:58Z · sase-xy.5.5.1] PROPOSED FOLLOW-UP: sase just check scoped lane fails ACE/LSP %dispatch parity against linked sase-core 0.32.40 — dispatch is gated by remote_dispatch in directive_contract() while tests/test_xprompt_directive_completion_parity.py still asserts it is ungated after skipping feature-flagged rows; phase 3 should reconcile this when ratcheting the published binding floor, not by weakening scanner/resolver tests.

[2026-09-08T01:18:33Z · sase-xy.5.5.1] Verified repository-owned source resolution in sase-core: stale attached checkouts fall through to live same-repo inventory; source_directory resolves one-component paths; files and ./directory targets share one decision path; distinct attached/inventory repos stay ambiguous; owner path_globs produce denied_filtered before any probe (typed document filters remain on resolve_document; host has no repository-source policy so path_globs is optional transport); matching HEAD is exact and a mismatched revision is unavailable_revision even when the worktree path exists. sase-core ./scripts/check.sh all passed (fmt, clippy, workspace tests including 19 repository_resolution tests and PyO3 stale-attached/source-dir/filter round-trip). Thin Python owner.path_globs wire plus document-source tests passed. Replaced a leftover _measure_section_heights call in pager/_layout.py (deleted in c92cee70) so mypy is green. sase just check lint gates passed; scoped tests 9812 passed / 4 failed, all four in tests/test_xprompt_directive_completion_parity.py (%dispatch vs remote_dispatch flag) — recorded as PROPOSED FOLLOW-UP, not a resolver regression.

## Dependencies

- **Blocks:** [sase-xy.5.5.2](sase-xy.5.5.2.md) ◐ · ⧖ 2026-09-07
- **Blocks:** [sase-xy.5.5.3](sase-xy.5.5.3.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.5.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.5.1/README.md) | [sase-xy.5.5.1](sase-xy.5.5.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d101fbd`](https://github.com/sase-org/sase/commit/d101fbd08657694233523cca298a526ada3b2609) | feat(artifact-ref): transport optional source path\_globs on document owner | [sase-xy.5.5.1](sase-xy.5.5.1.md) | 2026-09-07 21:20:08 EDT |
| sase-core | [`sase-core@885a61b`](https://github.com/sase-org/sase-core/commit/885a61bd819ab239b2058ef8d6ef5bb6cc051c8e) | fix(artifact-ref): make document source resolution repository-owned | [sase-xy.5.5.1](sase-xy.5.5.1.md) | 2026-09-07 21:22:18 EDT |
