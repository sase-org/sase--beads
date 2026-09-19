# Bead: sase-133.2 — Wire presentation facts

[Bead Pages](../README.md) / [sase-133](README.md) / sase-133.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0na](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0na.md) · **Assignee:** `sase-133.2` · **Size:** large
**Created:** 2026-09-18 16:37:59 EDT · **Closed:** 2026-09-18 19:13:25 EDT
**Plan:** [202609/remote\_dispatch\_agents\_tab\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_agents_tab_parity.md)

## Description

wire-presentation-facts: extend the fleet contract additively so every row carries the owner-presented display status, family/parent linkage for historical shells, resolved tribe/clan tribe, and both runtime timestamps, populated by the gateway projection and covered by golden wire fixtures.

## Notes

[2026-09-18T23:13:25Z · sase-133.2] Implemented owner presentation facts for fleet rows: schema v4 carries display status, run_started_at_unix, owner-resolved family lineage, tribe and clan tribe; gateway derives facts from the served record set; Python projection consumes the new run-start field. Verification: linked sase-core just check passed; primary just fmt passed; targeted Python tests for fleet contract, TUI fleet projection, machine status, and artifact-link batch path passed. Primary just check reached full-suite escalation and failed 17 unrelated completion/sidecar/TUI tests, recorded in final response.

## Dependencies

- **Depends on:** [sase-133.1](sase-133.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-133.3](sase-133.3.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.2.md) | [sase-133.2](sase-133.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`67614ee`](https://github.com/sase-org/sase/commit/67614ee2b01e6f2e6e2b8c6fe9fd21e4394b0956) | feat(fleet): consume owner presentation facts | [sase-133.2](sase-133.2.md) | 2026-09-18 20:08:07 EDT |
| sase-core | [`sase-core@11b8e06`](https://github.com/sase-org/sase-core/commit/11b8e060fe88d0a147b8449050d61a5f29038b9c) | feat(fleet): expose owner-resolved presentation facts | [sase-133.2](sase-133.2.md) | 2026-09-18 20:10:33 EDT |
