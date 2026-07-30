# Bead: sase-b5.2 — Anchor bead-page publication and refresh on the resolved primary repository

[Bead Pages](../README.md) / [sase-b5](README.md) / sase-b5.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b5.2` · **Size:** small
**Created:** 2026-07-30 11:20:12 UTC
**Plan:** [202607/bead\_page\_association\_anchors.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_page_association_anchors.md)

## Description

publish: stop letting the committing repository masquerade as the primary repository by routing the post-commit bead-page publication and the pages-refresh CLI through the shared resolver, so a commit made in a sidecar can no longer erase a lineage's associations.

## Dependencies

- **Depends on:** [sase-b5.1](sase-b5.1.md) ✓
- **Blocks:** [sase-b5.4](sase-b5.4.md) ◐
- **Blocks:** [sase-b5.5](sase-b5.5.md) ◐
