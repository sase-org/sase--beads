# Bead: sase-12p.2 — Detect and surface a running TUI whose editable checkout has advanced

[Bead Pages](../README.md) / [sase-12p](README.md) / sase-12p.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mq.md) · **Assignee:** `sase-12p.2` · **Size:** medium
**Created:** 2026-09-18 06:26:40 EDT · **Closed:** 2026-09-18 07:43:56 EDT
**Plan:** [202609/by\_status\_panels\_and\_stale\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202609/by_status_panels_and_stale_tui.md)

## Description

stale-process-restart: record the editable checkouts' imported git revisions at TUI startup, cheaply revalidate them on the existing update-status cadence, and when the deployed checkout has advanced past the running process surface a restart-to-load-new-code state in the Update panel and notifications wired to the existing restart-when-ready machinery, without adding render-path or keystroke cost.

## Notes

[2026-09-18T11:43:56Z · sase-12p.2] Implemented stale-running-code detection for editable runtime roots, update-panel restart surfacing, one-time stale notifications, and restart-when-ready wiring. Verified focused stale/update-panel tests and just check (scoped lane selected 116 files) pass; checked epic symbols before close and none remain.

## Dependencies

- **Blocks:** [sase-12p.3](sase-12p.3.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12p.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12p.2/README.md) | [sase-12p.2](sase-12p.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a6b072`](https://github.com/sase-org/sase/commit/3a6b072dd49c7e057a3b44009852c1f5ed31c318) | feat(tui): surface stale editable runtime code | [sase-12p.2](sase-12p.2.md) | 2026-09-18 07:45:47 EDT |
