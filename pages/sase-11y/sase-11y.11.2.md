# Bead: sase-11y.11.2 — Make the TUI surfaces describe the Services tab and service host

[Bead Pages](../README.md) / [sase-11y.11](sase-11y.11.md) / sase-11y.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.2` · **Size:** medium
**Created:** 2026-09-21 07:19:30 EDT · **Closed:** 2026-09-21 09:26:04 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

## Description

services-wording: relabel the quit modal's host-restart option, fix the Services-tab footer `x` hint, and rename the remaining Axe/AXE wording in the help title, onboarding guides, process-select modal, command-palette category, doctor next steps, and the screenshot example. Then regenerate and inspect the affected PNG goldens.

## Notes

[2026-09-21T12:47:40Z · sase-11y.11.2] PROPOSED FOLLOW-UP: visual goldens flake on the monitor/proc-shell badge timing — the top-strip badge renders at capture and settles by verify, failing fix-tui-screenshots determinism gates intermittently

[2026-09-21T12:49:46Z · sase-11y.11.2] PROPOSED FOLLOW-UP: visual runs trip the tmp-leak guard on codex-usage temp dirs — AceApp provider scans spawn codex app-server probes whose temp cwd outlives test teardown

[2026-09-21T13:26:04Z · sase-11y.11.2] services-wording done: quit modal relabeled to service host, Services footer x-hint dropped (bare x is no-op; host toggle is !x), help title Services, onboarding guides rewritten for host/procs/scheduler/oneshots, process modal Services Control, palette category Axe->Services, doctor next steps point at service host captured env, screenshot example -t services, tui_screenshot memory updated. Verified: 217 targeted tests green (footer/onboarding/quit/palette/doctor/screenshot/help), just fix clean, just check lint green except pre-existing sase-14j symvision findings in untouched _agent_bead_touches.py, 36 PNG goldens regenerated and band-inspected (footer/guide/title/palette changes only, plus pre-existing badge drift). 2 PROPOSED FOLLOW-UPs recorded (badge timing flake, codex-usage tmp-guard trips).

## Dependencies

- **Blocks:** [sase-11y.11.3](sase-11y.11.3.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.2/README.md) | [sase-11y.11.2](sase-11y.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3b7cfae`](https://github.com/sase-org/sase/commit/3b7cfae6f2446129d00a5fc3036109a0c50a5bd8) | feat(tui): describe the Services tab and service host across TUI surfaces | [sase-11y.11.2](sase-11y.11.2.md) | 2026-09-21 09:29:16 EDT |
