# Bead: sase-xe.16.10 — Runbook plus live Athena-to-Apollo end-to-end proof

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.10` · **Size:** medium
**Created:** 2026-09-08 10:21:40 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

live-apollo-proof: write the target-preparation runbook (docs/) covering supported Linux/macOS installation, gateway supervision and restart, loopback bind behind node-specific Tailscale Serve, bootstrap issuance, and enrollment recovery - then execute it live. Update the installed sase (and sase-core-rs) on athena and apollo, restart `sase axe` on both. On apollo over SSH: confirm the packaged `sase_gateway` resolves, run it supervised and loopback-bound at 127.0.0.1:7629, configure node-specific `tailscale serve` (HTTPS; guide through cert readiness if unmet), and issue `sase machine bootstrap --json`. On athena: run `sase machine init` end to end (tailnet discovery finds apollo as compatible, enrollment consumes the bundle, chezmoi change deploys, authenticated hello verifies), then verify `sase machine list`, `sase machine status apollo`, and deep doctor. Launch 1-3 xsmall remote agents with %dispatch:apollo on an eligible project, then drive them from athena using `sase ace --tmux` plus tmux send-keys / capture-pane: Fleet sub-view shows apollo with counts, follow a remote agent into Focus, and exercise remote management (view output, stop one launched agent). Verify a gateway restart on apollo does not break the enrollment. Record captured evidence on the phase bead. A Mac pass is best-effort only, never an acceptance gate.

## Notes

[2026-09-08T22:26:41Z · sase-xe.16.10] LIVE PROOF: Athena and Apollo both on sase 0.17.1+255.g338e3b349 with sase-core-rs 0.32.48. Packaged sase_gateway and sase_federation_worker resolve from $(uv tool dir)/sase/bin on both hosts.

[2026-09-08T22:27:05Z · sase-xe.16.10] LIVE PROOF: Apollo gateway is loopback-bound at 127.0.0.1:7629 under transient systemd user unit sase-gateway-proof.service (Restart=on-failure, MainPID sase_gateway). Local GET /api/v1/health returns status=ok, service=sase_gateway, fleet.supported_protocol_versions=[1].

[2026-09-08T22:27:28Z · sase-xe.16.10] LIVE PROOF: After Q1 Enabled, Apollo `tailscale serve --bg --yes 7629` still prints "Serve is not enabled on your tailnet" and waits on https://login.tailscale.com/f/serve?node=nyQhfbuXFj11CNTRL (timeout exit 124). `tailscale serve status` is "No serve config". CertDomains is null. Answering the SASE question does not toggle Tailscale admin Serve.

[2026-09-08T22:27:51Z · sase-xe.16.10] LIVE PROOF: `sase machine discover -j` finds apollo as builtin@tailnet candidate endpoint https://apollo.tail297af1.ts.net with compatibility=unknown and ConnectionRefusedError (HTTPS:443 not proxied). Mac and Pixel are offline/unknown as advisory. Controller registry still has zero enrolled machines.

[2026-09-08T22:28:13Z · sase-xe.16.10] RUNBOOK: Added docs/remote_dispatch.md and linked it from mkdocs.yml, docs/init.md, docs/mobile_gateway.md, docs/cli.md, and the `sase machine` CLI epilog. If a follow-up workspace checkout is clean, restore those files from this agent artifacts diff before continuing.

[2026-09-08T22:35:18Z · sase-xe.16.10] PROPOSED FOLLOW-UP: just check fails on unused public artifact_link_eligibility_wire_schema_version in src/sase/core/eligibility_facade.py (in-file + tests only; landed on master in dd1f829c2). Make it private and stop importing it from tests. Outside live-apollo-proof surfaces.

[2026-09-09T00:16:19Z · sase-xe.16.10] LIVE PROOF UPDATE: restored remote dispatch runbook docs/remote_dispatch.md and links (mkdocs nav, init, mobile gateway, CLI machine epilog); fixed symvision by making eligibility schema-version helper private and refreshed contract manifest. Verified CARGO_TARGET_DIR=/var/tmp/sase-core-target-sase13-release just check passed; mkdocs build --strict passed; focused parser/eligibility tests passed. Apollo gateway remains locally healthy on 127.0.0.1:7629 with supported_protocol_versions=[1], but tailscale serve --bg --yes 7629 still times out with "Serve is not enabled on your tailnet" and no Serve config; sase machine discover sees Apollo at https://apollo.tail297af1.ts.net but HTTPS health is ConnectionRefusedError. Bootstrap/enrollment/%dispatch proof remains blocked externally, so phase left open.

## Dependencies

- **Depends on:** [sase-xe.16.2](sase-xe.16.2.md) ✓ · ⧖ 2026-09-08
- **Depends on:** [sase-xe.16.3](sase-xe.16.3.md) ✓ · ⧖ 2026-09-08
- **Depends on:** [sase-xe.16.6](sase-xe.16.6.md) ✓ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.10.md) | [sase-xe.16.10](sase-xe.16.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`890660e`](https://github.com/sase-org/sase/commit/890660e257526d3c8fd1d78ec3e0ab53a062321c) | docs(dispatch): add remote setup runbook | [sase-xe.16.10](sase-xe.16.10.md) | 2026-09-08 20:49:56 EDT |
