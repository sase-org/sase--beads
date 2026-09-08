# Bead: sase-xe.16.10 — Runbook plus live Athena-to-Apollo end-to-end proof

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.10` · **Size:** medium
**Created:** 2026-09-08 10:21:40 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

live-apollo-proof: write the target-preparation runbook (docs/) covering supported Linux/macOS installation, gateway supervision and restart, loopback bind behind node-specific Tailscale Serve, bootstrap issuance, and enrollment recovery - then execute it live. Update the installed sase (and sase-core-rs) on athena and apollo, restart `sase axe` on both. On apollo over SSH: confirm the packaged `sase_gateway` resolves, run it supervised and loopback-bound at 127.0.0.1:7629, configure node-specific `tailscale serve` (HTTPS; guide through cert readiness if unmet), and issue `sase machine bootstrap --json`. On athena: run `sase machine init` end to end (tailnet discovery finds apollo as compatible, enrollment consumes the bundle, chezmoi change deploys, authenticated hello verifies), then verify `sase machine list`, `sase machine status apollo`, and deep doctor. Launch 1-3 xsmall remote agents with %dispatch:apollo on an eligible project, then drive them from athena using `sase ace --tmux` plus tmux send-keys / capture-pane: Fleet sub-view shows apollo with counts, follow a remote agent into Focus, and exercise remote management (view output, stop one launched agent). Verify a gateway restart on apollo does not break the enrollment. Record captured evidence on the phase bead. A Mac pass is best-effort only, never an acceptance gate.

## Dependencies

- **Depends on:** [sase-xe.16.2](sase-xe.16.2.md) ◐ · ⧖ 2026-09-08
- **Depends on:** [sase-xe.16.3](sase-xe.16.3.md) ◐ · ⧖ 2026-09-08
- **Depends on:** [sase-xe.16.6](sase-xe.16.6.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.10/README.md) | [sase-xe.16.10](sase-xe.16.10.md) | 0 |
