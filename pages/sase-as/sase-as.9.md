# Bead: sase-as.9 — ACE Plans pane over every document sidecar

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.9

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.9` · **Size:** medium
**Created:** 2026-07-29 14:31:29 UTC · **Closed:** 2026-07-29 15:46:01 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

ace-documents: browse and search documents from every configured document sidecar in the Artifacts Plans pane instead of only the plans sidecar, add a kind facet to its filter bar, show each row's kind, and update the ACE docs and help popup.

## Notes

[2026-07-29T15:46:01Z · sase-as.9] Implemented role-mapped ACE document archives, dynamic document-role kind filtering/completion, per-role failure isolation, shared honest archive caps, and ACE help/docs updates. Verified 123 focused data/filter/query tests and 7 Artifacts Plans PNG snapshots pass; full test-visual passed 370/373 with only three unrelated AXE description golden mismatches. just check passed formatting, Ruff, mypy, pyscripts, Symvision, and size lint, then stopped on pre-existing generated-skill drift and six missing/reverse prompt-link validation errors.

[2026-07-29T15:46:56Z · sase-as.9] Verified 123 focused tests and all 7 Artifacts Plans PNG snapshots; formatting, Ruff, mypy, Symvision, and size checks passed. Full visual suite had only 3 unrelated AXE golden mismatches, and repository validation stopped on pre-existing generated-skill and plan prompt-link drift.

## Dependencies

- **Depends on:** [sase-as.8](sase-as.8.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-as.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-as.9/README.md) | [sase-as.9](sase-as.9.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`880c9c8`](https://github.com/sase-org/sase/commit/880c9c891757ac2c1e3a29e6fc98f3ef2b056c31) | feat(ace): browse all document sidecars | [sase-as.9](sase-as.9.md) | 2026-07-29 15:47:26 |
