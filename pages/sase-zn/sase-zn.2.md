# Bead: sase-zn.2 — Replace the artifact-index N+1 reconcile and full dismissed-table rewrite

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.2` · **Size:** medium
**Created:** 2026-09-11 12:20:20 EDT · **Closed:** 2026-09-11 17:31:45 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

index-core-sql: in the linked sase-core repo, turn the per-candidate reconcile queries into set-based SQL and make the dismissed-identity projection a diff-based upsert instead of an unconditional 46k-row table replace.

## Notes

[2026-09-11T21:31:06Z · sase-zn.2] PROPOSED FOLLOW-UP: sase repo open sase-core fails with Unknown repo for project gh_sase-org__sase while sase repo list shows sase-core as a linked cloned repo — list and open resolve against different inventories (already noted in the epic plan for the verify phase to file).

[2026-09-11T21:31:45Z · sase-zn.2] Set-based dismissed-family reconcile (2 SQL reads + batched inserts, not N+1) and diff-based dismissed-table replace with force full-rewrite. Verified: sase-core cargo fmt, clippy -D warnings, dismissal_reconcile_* and dismissed_replace_diffs tests (including 40k dismissed + 10k artifact fixture matching the old N+1 results with <16 statements); sase-core cargo test --workspace on 0.34.11; Python ruff + 32 lifecycle/cli tests; mypy on the adapter files. Schema version stays 27 (existing dismissed/family indexes already cover the new queries).

## Dependencies

- **Blocks:** [sase-zn.5](sase-zn.5.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.2/README.md) | [sase-zn.2](sase-zn.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ace0de2`](https://github.com/sase-org/sase/commit/ace0de26771479759eaf03614da1bf6098559e92) | feat(agent-scan): pass force through dismissed projection replace | [sase-zn.2](sase-zn.2.md) | 2026-09-11 17:33:58 EDT |
| sase-core | [`sase-core@34b3229`](https://github.com/sase-org/sase-core/commit/34b32290ac2bd643a5b66b9835b4e3f4410ed2bf) | feat(agent-scan): set-based dismissed-family reconcile and diff replace | [sase-zn.2](sase-zn.2.md) | 2026-09-11 17:36:50 EDT |
