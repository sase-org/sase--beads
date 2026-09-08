# Bead: sase-xy.5.5.4.1 — Bound source-directory resolution to proved owner provenance

[Bead Pages](../README.md) / [sase-xy.5.5.4](sase-xy.5.5.4.md) / sase-xy.5.5.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xy.5.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xy.5.5.land.md) · **Assignee:** `sase-xy.5.5.4.1` · **Size:** medium
**Created:** 2026-09-07 23:17:39 EDT · **Closed:** 2026-09-07 23:45:30 EDT
**Plan:** [202609/finish\_pager\_target\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_pager_target_ownership.md)

## Description

prove-owner-provenance: make source-directory and project identity constrain repository selection in Rust, rejecting out-of-inventory or mismatched provenance without regressing stale-checkout fallback, revision checks, filters, directories, ambiguity, or bounded search.

## Notes

[2026-09-08T03:45:30Z · sase-xy.5.5.4.1] Verified source-directory hits require containment in an attached or inventory checkout: an out-of-inventory directory with secret.py is no longer relabeled as repository owner (proven_missing). Covered owner-repository mismatch, owner-project mismatch, unavailable project context, nested source directory with project agreement, correlated producer workspace without inventory, and stale-source fallback to a live same-repo checkout. Existing directory, filter, revision, ambiguity, traversal, and suffix-budget cases still pass. sase-core just check green including the PyO3 out-of-inventory rejection. sase just check green for selected_project on the context wire and owner-project passthrough into artifact_ref_context.

## Dependencies

- **Blocks:** [sase-xy.5.5.4.3](sase-xy.5.5.4.3.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.5.5.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.5.5.4.1/README.md) | [sase-xy.5.5.4.1](sase-xy.5.5.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eccc091`](https://github.com/sase-org/sase/commit/eccc0916048d844dfeaa64ee13ae4a411df2cd35) | fix(artifact-ref): send selected\_project and honor owner project in context assembly | [sase-xy.5.5.4.1](sase-xy.5.5.4.1.md) | 2026-09-07 23:46:50 EDT |
