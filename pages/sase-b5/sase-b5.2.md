# Bead: sase-b5.2 — Anchor bead-page publication and refresh on the resolved primary repository

[Bead Pages](../README.md) / [sase-b5](README.md) / sase-b5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b5.2` · **Size:** small
**Created:** 2026-07-30 11:20:12 UTC · **Closed:** 2026-07-30 12:38:20 UTC
**Plan:** [202607/bead\_page\_association\_anchors.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_page_association_anchors.md)

## Description

publish: stop letting the committing repository masquerade as the primary repository by routing the post-commit bead-page publication and the pages-refresh CLI through the shared resolver, so a commit made in a sidecar can no longer erase a lineage's associations.

## Notes

[2026-07-30T12:38:20Z · sase-b5.2] Implemented checkout-anchor routing for bead-page publication, refresh, page URLs, bead links, and association building. Verified focused bead-page pytest, just _lint-symvision, and just test: 24184 passed, 7 skipped. just check passes lint stages but is blocked by unrelated plan-links validation for 202607/editor_artifact_ref_parity.md.

## Dependencies

- **Depends on:** [sase-b5.1](sase-b5.1.md) ✓
- **Blocks:** [sase-b5.4](sase-b5.4.md) ✓
- **Blocks:** [sase-b5.5](sase-b5.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b5.2/README.md) | [sase-b5.2](sase-b5.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`5ba1f08`](https://github.com/sase-org/sase/commit/5ba1f08d0262d14300f295b60b8fee2df3866d50) | fix: anchor bead page publication on primary checkout | [sase-b5.2](sase-b5.2.md) | 2026-07-30 12:39:39 |
