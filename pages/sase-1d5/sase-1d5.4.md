# Bead: sase-1d5.4 — Public attachments sidecar, routing, and anonymous reads

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.4` · **Size:** large
**Created:** 2026-09-30 01:57:13 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1da][1] | sase-1d5.4 rewrites discover_stores and hidden_clone_path per role; honor the disabled flag in that new per-role discovery |
| related | [bead:sase-1db][2] | sase-1d5 adds the anonymous remote_visibility probe this check should reuse for the attachments-private remote |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1da/README.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1db/README.md

<!-- sase:links:end -->

## Description

public_store: spike the page-embed path, then add the reserved hidden public attachments role (injected only for public beads, with PUBLIC default-yes consent and a beads-visibility guard). Covers the HTTPS-fetch/SSH-push bare clone with read-side auto-materialization, a role-parameterized GitAttachmentStore with extension-preserving layout, placement and outbox by audience with no cross-audience fallback, GH013 handling, fixes to the fetch-miss and lazy-discovery bugs, and purge and doctor coverage.

## Dependencies

- **Depends on:** [sase-1d5.3](sase-1d5.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.5](sase-1d5.5.md) ◐ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.6](sase-1d5.6.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.4/README.md) | [sase-1d5.4](sase-1d5.4.md) | 0 |
