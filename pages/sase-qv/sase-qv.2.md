# Bead: sase-qv.2 — Required start and stop status flags

[Bead Pages](../README.md) / [sase-qv](README.md) / sase-qv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.2` · **Size:** medium
**Created:** 2026-08-19 09:14:32 EDT · **Closed:** 2026-08-19 10:51:59 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

cli: make -s/--start-status and -S/--stop-status required on sase monitor start, clamp over-length labels with a warning, make the two fields required on StartMonitorRequest, and render the effective label in sase monitor list, show, markdown, and JSON.

## Notes

[2026-08-19T14:51:15Z · sase-qv.2] PROPOSED FOLLOW-UP: ci — tools/validate_sase_core_rs first-writer probe fails against sase-core 0.29.1 because provider_disable_try_set_relative now takes a string mode and the probe still passes a float duration as that argument, so just check _setup cannot rebuild the wheel

[2026-08-19T14:51:32Z · sase-qv.2] PROPOSED FOLLOW-UP: just check — Justfile still has --epic-symbol entries for closed bead sase-qt.4 (MemoryNoteDigest, MemoryPanelInitialLoad, MemoryRailNode, filter_memory_notes, invalidate_memory_scope, load_memory_panel_initial_state); symvision refuses them as stale

[2026-08-19T14:51:59Z · sase-qv.2] CLI phase: -s/--start-status and -S/--stop-status are required on sase monitor start (handler exit 2 with teaching text); over-length labels clamp to 20 chars with a stderr warning; empty/multiline still exit 2. StartMonitorRequest now requires both fields and clamps in __post_init__ (TypeError if omitted; over-length never reaches agent_meta.json). list/show/markdown/JSON render the effective pair label; JSON schema is v2 with status_label + status_accent. Plugin repos (sase-github, sase-telegram, sase-nvim, sase-research-artifacts) have no sase monitor start callers. epic-symbols sase-qv.2 is empty after wiring clamp/effective/accent/glyph/style. Verified: ruff format/check + mypy on src; toobig; targeted pytest for handler start/list/show/stop, parser help, render surfaces, StartMonitorRequest constructors, epic_launch, followup/ack/supervisor. just check _setup is blocked by the sase-core 0.29.1 provider-disable probe (see PROPOSED FOLLOW-UP).

[2026-08-19T14:53:27Z · sase-qv.2] CLI phase: -s/--start-status and -S/--stop-status are required on sase monitor start (handler exit 2 with teaching text); over-length labels clamp to 20 chars with a stderr warning; empty/multiline still exit 2. StartMonitorRequest now requires both fields and clamps in __post_init__. list/show/markdown/JSON render the effective pair label; JSON schema is v2 with status_label + status_accent. Plugin repos have no sase monitor start callers. epic-symbols sase-qv.2 is empty. Verified: ruff format/check + mypy on src; targeted pytest for handler start/list/show/stop, parser help, render surfaces, StartMonitorRequest constructors, epic_launch, followup/ack/supervisor. just check _setup is blocked by the sase-core 0.29.1 provider-disable probe (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-qv.1](sase-qv.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qv.7](sase-qv.7.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.2/README.md) | [sase-qv.2](sase-qv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a64acb2`](https://github.com/sase-org/sase/commit/a64acb267e3e3435589b167fdeaebbcd04ab93bb) | feat(monitor)!: require start and stop status flags on monitor start | [sase-qv.2](sase-qv.2.md) | 2026-08-19 11:07:24 EDT |
