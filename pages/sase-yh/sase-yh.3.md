# Bead: sase-yh.3 — Retry and report aging artifact-link publications

[Bead Pages](../README.md) / [sase-yh](README.md) / sase-yh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08g.md) · **Assignee:** `sase-yh.3` · **Size:** medium
**Created:** 2026-09-08 12:24:41 EDT · **Closed:** 2026-09-08 15:41:19 EDT
**Plan:** [202609/stitch\_resume\_publication\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202609/stitch_resume_publication_recovery.md)

## Description

publication: complete sase-ye by persisting retry state for hidden document sidecars and sweeping unpublished work without requiring new mutations, with bounded backoff, ownership checks, and aging diagnostics.

## Notes

[2026-09-08T19:41:19Z · sase-yh.3] Implemented durable artifact-link publication retry state and sweep integration; verified cargo fmt --check, cargo test -p sase_core publication_retry, cargo test -p sase_core_py artifact_ref_contract_bindings_round_trip_json_shapes, focused pytest retry/sync/validator suites, and TMPDIR=/home/bryan/tmp/sase CARGO_TARGET_DIR=/home/bryan/tmp/sase/sase-yh3-cargo-target just check (full-suite escalation passed).

## Dependencies

- **Blocks:** [sase-yh.4](sase-yh.4.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yh.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yh.3/README.md) | [sase-yh.3](sase-yh.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`46f7f54`](https://github.com/sase-org/sase/commit/46f7f549ef2edc9d4e7f9136d810786cb9792b48) | fix(sdd): retry unpublished artifact-link sidecars | [sase-yh.3](sase-yh.3.md) | 2026-09-08 16:48:27 EDT |
| sase-core | [`sase-core@ff0a72e`](https://github.com/sase-org/sase-core/commit/ff0a72e1f060130d34e49af4c8b8ba94666db453) | feat(artifact-link): add publication retry policy | [sase-yh.3](sase-yh.3.md) | 2026-09-08 16:50:16 EDT |
