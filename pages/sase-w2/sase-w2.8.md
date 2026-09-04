# Bead: sase-w2.8 — Family grouping and provenance in ACE

[Bead Pages](../README.md) / [sase-w2](README.md) / sase-w2.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.8--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.8.md) · **Assignee:** `sase-w2.8` · **Size:** medium
**Created:** 2026-09-03 12:32:10 EDT · **Closed:** 2026-09-04 03:26:04 EDT
**Plan:** [202609/athena\_agent\_sync\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/athena_agent_sync_repair.md)

## Description

imported-family-ui: materialize imported family containers as root rows so members fold under them, quarantine hoods whose members lack a container, and surface imported_source_owner as an owner badge in rows, detail pane, and neighbor roster.

## Notes

[2026-09-04T07:25:23Z · sase-w2.8--3] PROPOSED FOLLOW-UP: just check still passes with core-floor-probe stale_actionable — declared sase-core-rs floor is 0.32.16 while published sase-core v0.32.17/v0.32.18 already contain 12 capabilities from sase-w3.1 artifact-row resolution and sase-w2.6 typed owner identity. This phase also added unpublished imported_source_owner on the scan wire; bump the declared floor after the next sase-core release that includes it.

[2026-09-04T07:26:04Z · sase-w2.8--3] Verified imported-family-ui: ACE materializes imported family containers as root rows so --plan/--code/--mon members fold under one family with no --code orphan roots; revival restores that synthetic root plus members under one family; owner badges render for foreign-machine (athena) and foreign-user (bob@zeus) on rows, detail pane, neighbor roster, and revival labels; v2 import quarantines a hood whose family members lack a container. sase-core copies imported_source_owner through AgentMeta/DoneMarker scan wire with live-scan parity. Targeted tests and just check (2212 scoped files, 38m56s, exit 0) passed. epic-symbols sase-w2.8 reported no leftovers.

## Dependencies

- **Depends on:** [sase-w2.4](sase-w2.4.md) ✓ · ⧖ 2026-09-03
- **Depends on:** [sase-w2.6](sase-w2.6.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w2.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w2.8.md) | [sase-w2.8](sase-w2.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5ab116d`](https://github.com/sase-org/sase/commit/5ab116df73f32f87c73174881b13e70b3d27e296) | feat(ace): group imported families and surface owner badges | [sase-w2.8](sase-w2.8.md) | 2026-09-04 03:27:49 EDT |
