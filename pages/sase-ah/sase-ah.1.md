# Bead: sase-ah.1 — Resolve the publication project from the committed repository path

[Bead Pages](../README.md) / [sase-ah](README.md) / sase-ah.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ah.1` · **Size:** medium
**Created:** 2026-07-28 18:19:14 UTC · **Closed:** 2026-07-28 19:51:11 UTC
**Plan:** [202607/agent\_publication\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_publication_reliability.md)

## Description

target-resolution: resolve the post-commit publication target by matching the commit's repository path against the repo inventory (including workspace clones) so sidecar and linked-repo commits publish to the host project, and stop the auxiliary publication step from failing a commit that already landed.
