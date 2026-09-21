# Bead: sase-11y.11.2 — Make the TUI surfaces describe the Services tab and service host

[Bead Pages](../README.md) / [sase-11y.11](sase-11y.11.md) / sase-11y.11.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.2` · **Size:** medium
**Created:** 2026-09-21 07:19:30 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

## Description

services-wording: relabel the quit modal's host-restart option, fix the Services-tab footer `x` hint, and rename the remaining Axe/AXE wording in the help title, onboarding guides, process-select modal, command-palette category, doctor next steps, and the screenshot example. Then regenerate and inspect the affected PNG goldens.

## Notes

[2026-09-21T12:47:40Z · sase-11y.11.2] PROPOSED FOLLOW-UP: visual goldens flake on the monitor/proc-shell badge timing — the top-strip badge renders at capture and settles by verify, failing fix-tui-screenshots determinism gates intermittently

[2026-09-21T12:49:46Z · sase-11y.11.2] PROPOSED FOLLOW-UP: visual runs trip the tmp-leak guard on codex-usage temp dirs — AceApp provider scans spawn codex app-server probes whose temp cwd outlives test teardown

## Dependencies

- **Blocks:** [sase-11y.11.3](sase-11y.11.3.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.2/README.md) | [sase-11y.11.2](sase-11y.11.2.md) | 0 |
