# Bead: sase-bv.1 — Record an explicit creator in sase-core bead creation and plan validation

[Bead Pages](../README.md) / [sase-bv](README.md) / sase-bv.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bv.1` · **Size:** medium
**Created:** 2026-07-31 13:12:31 UTC · **Closed:** 2026-07-31 13:42:09 UTC
**Plan:** [202607/bead\_created\_by\_attribution.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_created_by_attribution.md)

## Description

core: add an optional `created_by` to the Rust bead-create request with an explicit request/phase-parent/store-owner resolution order, and add the optional system-managed `proposed_by` plan frontmatter field to the plan validator, schema, and validated wire.

## Notes

[2026-07-31T13:27:25Z · sase-bv.1] PROPOSED FOLLOW-UP: Remove stale Symvision epic-symbol exemptions for sase-bj.3 — `just check` reports both `CommitMessagePolicy` and `CommitSubject` exemptions reference a closed bead and require cleanup.

[2026-07-31T13:41:03Z · sase-bv.1] PROPOSED FOLLOW-UP: Restore the unrelated main-suite verification baseline — after excluding the expected `proposed_by` Python-facade mismatch owned by phase sase-bv.2, `just test` still had 55 failures spanning model-catalog metadata, worker-capacity contention, and broad ACE visual snapshots; `sase validate` also reports generated-provider-skill drift and a missing prompt-to-plan link.

[2026-07-31T13:42:09Z · sase-bv.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and installed PyO3 smoke checks for explicit created_by plus validated proposed_by; just install and committed-plan validation also passed. Unrelated main-workspace baseline failures were recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Blocks:** [sase-bv.2](sase-bv.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bv.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bv.1/README.md) | [sase-bv.1](sase-bv.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@69429ae`](https://github.com/sase-org/sase-core/commit/69429ae600695e96f7c47e16bfe620bb46db8545) | feat: preserve bead proposal attribution | [sase-bv.1](sase-bv.1.md) | 2026-07-31 13:43:36 |
