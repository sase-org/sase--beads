# Bead: sase-12y.2 — Batch and bound artifact-link projection in SASE

[Bead Pages](../README.md) / [sase-12y](README.md) / sase-12y.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.0k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.0k.md) · **Assignee:** `sase-12y.2` · **Size:** medium
**Created:** 2026-09-18 09:48:00 EDT · **Closed:** 2026-09-18 14:29:10 EDT
**Plan:** [202609/artifact\_link\_projection\_timeout.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_projection_timeout.md)

## Description

deadline_aware_projection: pin the published core capability, route full-truth bead projection through bounded batches, and propagate the chop deadline so partial progress is committed and safely retried instead of being SIGKILLed.

## Notes

[2026-09-18T18:29:10Z · sase-12y.2--1] Verified core pin ratchet (sase-core-revision.txt + tools/validate_sase_core_rs capability probe), batch projection wrappers (set_link_projections / set_bead_endpoint_projections) with bounded apply_events_to_beads batches and deadline deferral through persist/drain/publish/chop, focused suites (bead mutation, artifact-link beads/derivation/outbox/backfill, projection batch, bindings), and just check.

## Dependencies

- **Depends on:** [sase-12y.1](sase-12y.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12y.3](sase-12y.3.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-12y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-12y.2.md) | [sase-12y.2](sase-12y.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2d46e2c`](https://github.com/sase-org/sase/commit/2d46e2cf40344859990dab39b094cad78b24640d) | feat(sdd): bound artifact-link projection with deadline-aware batches | [sase-12y.2](sase-12y.2.md) | 2026-09-18 14:35:31 EDT |
