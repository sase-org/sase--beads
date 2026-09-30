# Bead: sase-1d5.4 — Public attachments sidecar, routing, and anonymous reads

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.4` · **Size:** large
**Created:** 2026-09-30 01:57:13 EDT · **Closed:** 2026-09-30 12:41:31 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1da][1] | sase-1d5.4 rewrites discover_stores and hidden_clone_path per role; honor the disabled flag in that new per-role discovery |
| related | [bead:sase-1db][2] | sase-1d5 adds the anonymous remote_visibility probe this check should reuse for the attachments-private remote |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1da/README.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1db/README.md

<!-- sase:links:end -->

## Description

public_store: spike the page-embed path, then add the reserved hidden public attachments role (injected only for public beads, with PUBLIC default-yes consent and a beads-visibility guard). Covers the HTTPS-fetch/SSH-push bare clone with read-side auto-materialization, a role-parameterized GitAttachmentStore with extension-preserving layout, placement and outbox by audience with no cross-audience fallback, GH013 handling, fixes to the fetch-miss and lazy-discovery bugs, and purge and doctor coverage.

## Notes

[2026-09-30T16:16:18Z · sase-1d5.4] Page-embed spike (public_store Step 1, read-only): curl -I shows .png in sase--research serves image/png with nosniff, while extensionless objects serve text/plain with nosniff per report S1. gh api markdown renders both ![x](<blob URL>?raw=true) and the raw URL as <img> (camo on render). Finding for presentation phase: bead pages should embed public images via the raw URL form (blob ?raw=true also embeds, raw is canonical); extensionless objects cannot embed and pages must link instead of embedding. Extension-preserving public layout stays regardless: raw content type depends on it.

[2026-09-30T16:41:12Z · sase-1d5.4--1] PROPOSED FOLLOW-UP: tools/validate_sase_core_rs prompt-prediction probe fails on clean base (exit 1, confident False, ghost [], support 3 vs min_support 4). Reproduces identically with public_store changes stashed (git stash, validator exit 1 same output, stash pop). Root cause is sase-core cfc6385 correctness fix that stopped double-counting project-boost support; validator 3-row fixture no longer reaches balanced min_support 4. Unrelated to public_store diff (no validator/core/prompt files touched). just check _setup blocks at line 141 on this; relevant attachment suites pass directly.

[2026-09-30T16:41:31Z · sase-1d5.4--1] public_store landed and verified: 11 two-home public_store tests, 52 attachment git/fetch/upload/lifecycle/sidecar-bare tests, 32 repo-init/hidden-agent tests pass; ruff clean; mypy clean on 533 files; symvision clean for phase symbols (7 remaining unused are pre-existing tool/ files); sase bead epic-symbols clean. just check _setup still red on clean base due to pre-existing validate_sase_core_rs prompt-prediction probe (see PROPOSED FOLLOW-UP note).

## Dependencies

- **Depends on:** [sase-1d5.3](sase-1d5.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.5](sase-1d5.5.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.6](sase-1d5.6.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.4.md) | [sase-1d5.4](sase-1d5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`80f64cc`](https://github.com/sase-org/sase/commit/80f64cc20b598f10f8c8df01dc8a224eead45210) | feat(bead-attachments): public attachments sidecar, routing, and anonymous reads (sase-1d5.4) | [sase-1d5.4](sase-1d5.4.md) | 2026-09-30 12:44:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d5.4--1][1] | confirm closure for handoff | 2 |
| read-by | [agent:sase-1d5.6][2] | Need public_store spike finding on page-embed URL form | 2 |
| read-by | [agent:sase-1d5.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.6/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.land/README.md

<!-- sase:referenced-by:end -->
