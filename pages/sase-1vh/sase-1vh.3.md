# Bead: sase-1vh.3 — SQLite extended codes in sase-core busy lookup diagnostics

[Bead Pages](../README.md) / [sase-1vh](README.md) / sase-1vh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gu](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gu.md) · **Assignee:** `sase-1vh.3` · **Size:** small
**Created:** 2026-11-26 14:45:31 EST · **Closed:** 2026-11-26 15:42:14 EST
**Plan:** [202611/launch\_lookup\_busy\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202611/launch_lookup_busy_resilience.md)

## Description

busy-diagnostics: in sase-core, decorate busy/locked SQLite errors on the artifact-index and dismissed-bundle lookup read paths with the extended code, keeping busy classification, wire shapes, and bindings unchanged.

## Notes

[2026-11-26T20:42:14Z · sase-1vh.3] busy-diagnostics done in sase-core: sqlite_error_diagnostic decorates DatabaseBusy/DatabaseLocked as '{error} (extended_code=N)' on the artifact-index lookup read path (storage open/busy-timeout/schema-version/alias-resolve + query prepare/step) and the dismissed-bundle path (open_named_lookup_store + query prepare/step, incl. ArchiveStoreError::From); classification unchanged (decorated text still contains locked/busy), no wire/binding changes. Tests: busy fixtures now assert availability=Busy plus diagnostic contains extended_code=; forced-unavailability keeps no diagnostic. Verified: lookup suite 24 passed, archive store suite 26 passed, full sase tool run check verdict pass. Changes left uncommitted in sase-core checkout for review.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vh.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.3/README.md) | [sase-1vh.3](sase-1vh.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2efa9f6`](https://github.com/sase-org/sase-core/commit/2efa9f6b97fed27fe2fd34e09c59150cb437b325) | fix(agent-scan): report SQLite extended codes in busy lookup diagnostics | [sase-1vh.3](sase-1vh.3.md) | 2026-11-26 15:43:43 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vh.3][1] | check phase notes and remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.3/README.md

<!-- sase:referenced-by:end -->
