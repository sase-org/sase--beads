# Bead: sase-b5.3 — Resolve agent links from any repository in the workspace

[Bead Pages](../README.md) / [sase-b5](README.md) / sase-b5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b5.3` · **Size:** medium
**Created:** 2026-07-30 11:20:18 UTC · **Closed:** 2026-07-30 12:38:03 UTC
**Plan:** [202607/bead\_page\_association\_anchors.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_page_association_anchors.md)

## Description

agentlinks: make the hosted agents-sidecar remote lookup and the SASE_AGENT commit-footer tag resolve the owning project through the shared resolver instead of naming the current working directory's repository, so agent labels stop rendering and committing unlinked.

## Notes

[2026-07-30T12:38:03Z · sase-b5.3] Implemented checkout-anchor project/root resolution for hosted agent URLs and SASE_AGENT commit tags. Verified 26 focused link tests, full suite (24187 passed, 7 skipped), formatting/lint including Symvision, SASE and committed-plan validation, git diff check, and live linked footer resolution from both plans sidecar and sase-core linked checkout.

[2026-07-30T12:38:58Z · sase-b5.3] Verified 26 focused tests, full suite (24187 passed, 7 skipped), formatting/lint including Symvision, SASE and committed-plan validation, and live sidecar/linked-repo footer resolution.

## Dependencies

- **Depends on:** [sase-b5.1](sase-b5.1.md) ✓
- **Blocks:** [sase-b5.5](sase-b5.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b5.3/README.md) | [sase-b5.3](sase-b5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`f1289a1`](https://github.com/sase-org/sase/commit/f1289a124ba4e94478b2ea0f973344c8a96ebc46) | fix: resolve agent links through checkout anchors | [sase-b5.3](sase-b5.3.md) | 2026-07-30 12:39:25 |
