# Bead: sase-xy.5.2 — Resolve targets using document ownership and repository identity

[Bead Pages](../README.md) / [sase-xy.5](sase-xy.5.md) / sase-xy.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03o--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03o.md) · **Assignee:** `sase-xy.5.2` · **Size:** medium
**Created:** 2026-09-07 13:01:42 EDT · **Closed:** 2026-09-07 17:54:51 EDT
**Plan:** [202609/pager\_target\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_target_integrity.md)

## Description

repository-resolution: add shared provenance and repository-aware candidate selection, retaining owner context, bounded lookup, ambiguity, and resolution evidence.

## Notes

[2026-09-07T21:54:18Z · sase-xy.5.2] PROPOSED FOLLOW-UP: repository-scoped source-path resolution (resolve_document_source_target) has no permission/glob-filter policy analogous to document_roots/file_roots path_globs — ArtifactRefTargetFailureCategoryWire::DeniedFiltered is defined but currently unreachable; add per-repository path_globs to ArtifactRefRepositoryWire if source-path access needs restricting.

[2026-09-07T21:54:51Z · sase-xy.5.2] Added sase-core Rust module artifact_ref/repository_resolution.rs (resolve_document_source_target) plus wire types (ArtifactRefDocumentOwnerWire, ArtifactRefTargetResolutionWire/CandidateWire/FailureCategoryWire) implementing repository-identity-aware resolution: attached checkouts, explicit/scoped repository inventory search, other checkouts of the same repo, and a bounded (20k-entry budget) suffix search for drifted paths, with ambiguity/missing-checkout/proven-missing/temporary-error outcomes and per-repo dedup so copies of one repo never create false ambiguity. Added PyO3 binding (artifact_ref_resolve_document_source_target + schema-version getter) and Python adapter (ArtifactRefDocumentOwner/ArtifactRefTargetResolution/ArtifactRefTargetCandidate models, artifact_ref_operations.resolve_document_source_target, facade exports). Verified: 10 new Rust unit tests (owning-repo resolution, unrelated same-name-file rejection, ambiguous linked repos, deleted-producer-workspace fallback to live alternate checkout, absent-checkout retryability, drifted suffix match, explicit-repository scoping, attached-checkout precedence, traversal rejection) plus an extended PyO3 binding round-trip test all pass; sase-core's scripts/check.sh all (fmt-check, clippy -D warnings, full cargo test --workspace) passed; rebuilt/installed the sase_core_rs extension via just rust-install; 4 new focused Python tests plus the full tests/artifact_refs/ suite (109 passed) pass; sase's just check (fmt, all lint gates, SASE validation, scoped test escalated to full suite on core-identity-changed) passed. epic-symbol guard clean (no --epic-symbol entries).

## Dependencies

- **Depends on:** [sase-xy.5.1](sase-xy.5.1.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-xy.5.3](sase-xy.5.3.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.2/README.md) | [sase-xy.5.2](sase-xy.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d8a299c`](https://github.com/sase-org/sase/commit/d8a299c2c3e401d9a08f5802849c15afb3eceb7b) | feat(pager-refs): add Python adapter for document-owned source-path resolution | [sase-xy.5.2](sase-xy.5.2.md) | 2026-09-07 17:56:02 EDT |
