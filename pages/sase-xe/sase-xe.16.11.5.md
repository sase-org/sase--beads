# Bead: sase-xe.16.11.5 — Complete the real Athena-to-Apollo workflow

[Bead Pages](../README.md) / [sase-xe.16.11](sase-xe.16.11.md) / sase-xe.16.11.5

**Status:** ○ open · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.5` · **Size:** medium
**Created:** 2026-09-09 04:38:30 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

## Previously Closed

> ↺ Closed 2026-09-09T16:02:53Z · done
>
> (none)
>
> Reopened 2026-09-09T16:12:23Z by `sase bead open`

## Description

live-apollo-acceptance: finish the reopened sase-xe.16.10 acceptance using node-specific Tailscale Serve, fresh installed builds, canonical init, authenticated status, remote launches, TUI follow/output/stop, and gateway restart recovery; retain redacted command and pane evidence.

## Notes

[2026-09-09T15:37:15Z · sase-xe.16.11.5] LIVE PROOF: Athena sase 0.17.1+302.g20c7b9804 with sase-core-rs 0.32.54+1.ga6d40bad1; Apollo pulled to the same sase SHA and core a6d40ba. Packaged sase_gateway/sase_federation_worker resolve from uv-tool bin. After rebuild, both loopback and HTTPS https://apollo.tail297af1.ts.net/api/v1/health return status=ok, service=sase_gateway, version=0.32.54, fleet.supported_protocol_versions=[1]. tailscale serve status on Apollo is node-specific HTTPS root proxying 127.0.0.1:7629 (no Funnel). systemd user unit sase-gateway.service is the live supervisor (not sase-gateway-proof).

[2026-09-09T15:37:38Z · sase-xe.16.11.5] LIVE PROOF: Canonical sase machine init -B <protected file> on Athena: discovery listed apollo as candidate 1 (builtin@tailnet, compatible), Mac HTTP 502, Pixel timeout/offline advisory. Selected 1, alias apollo. Result: apollo enrolled as sase-host. sase machine list shows alias apollo, provider builtin@tailnet, endpoint https://apollo.tail297af1.ts.net, not quarantined. sase machine status apollo: ok, hello ok, protocol 1, fleet.hello/launch/catalog/mutate capabilities. sase doctor -D -C dispatch: OK (4 checks). Chezmoi source and applied sase_athena.yml both contain dispatch.apollo. Bootstrap files removed on both hosts. Init PTY waiter hit 300s after the enrolled line printed; enrollment/hello were already durable.

[2026-09-09T15:38:01Z · sase-xe.16.11.5] LIVE PROOF: ACE --tmux Fleet after adapter fix shows Apollo rows with readable names (bob-cli, sase, gates/monitors), 153 catalog rows including 97 done, machine count 1, Fleet chip running=1 (authoritative, not page-row count). Follow of apollo row "a" updated follow state; Focus then showed star apollo [agent] sase (RUNNING) a with Machine: apollo followed. View remote content toasted "Remote content is not available" for that stale row (no prompt file). Gateway restart (0.32.54 rebuild plus later unit restart) left status hello ok with the same installation id.

[2026-09-09T15:38:23Z · sase-xe.16.11.5] UNMET GATE: Athena %dispatch:apollo launch of an xsmall observation agent. Dirty controller checkout is rejected (must launch from a clean published tree or Patch evidence). After a clean tree, systemd PATH lacked sase so agent_bridge was unavailable; unit now sets PATH plus --agent-bridge-command to the installed sase binary (runbook updated). Target then failed unknown mobile project context: sase because Apollo stores the project as gh_sase-org__sase; a local alias path plus known_project_file alias resolution were added. A later unique-prompt launch started on Apollo (bridge EXIT 0, name dispatch-bfb532e258f60266af7d29957c8a7c8e, pid 610568, workspace sase_11, ace(run)-260909_105945) but Athena reported request deadline elapsed, so ACE had no receipt. Fleet catalog did not show the new row among 153, so Athena sase machine agent stop by name did not match. TUI stop/output of that launched agent from Athena was not completed. The stray target process was killed on Apollo after evidence capture.

[2026-09-09T15:38:46Z · sase-xe.16.11.5] PROPOSED FOLLOW-UP: Fleet/Focus now decodes worker catalog payload.page.rows, followed-batch entries[].summary, host errors, legal page size 100 with include_terminal and cursor merge, logical_keys, labels.agent_label/provider/intent, and payload.counts running. Extract request validation, envelope normalization, and count aggregation into sase-core with ACE-generated request regression tests as the research report asked; Python adapter is the live unblock.

[2026-09-09T15:39:08Z · sase-xe.16.11.5] PROPOSED FOLLOW-UP: Remote launch receipt deadline is shorter than target-side sase mobile agent-bridge launch-text when PROJECT_NAME alias conflicts spam the log; Athena marks uncertain while Apollo actually starts the agent. Raise the controller wait or make the target launch faster/ quieter, and surface bridge stderr in the LaunchFailed error instead of only agent_bridge:launch-text.

[2026-09-09T15:39:32Z · sase-xe.16.11.5] PROPOSED FOLLOW-UP: Fleet catalog hydration did not include a just-launched Apollo running agent in the same ACE session (153 rows / Fleet chip 1 unchanged). Force a cache-busting catalog after a dispatch receipt, and make sase machine agent stop resolve operation-id names like dispatch-<hex> / ace(run)-<stamp> from the target, not only currently projected Fleet rows.

[2026-09-09T16:02:53Z · sase-xe.16.11.5] Auto-closed by `sase stitch create` after create_commit landed b7c6bc006 ("fix(ace): decode live Fleet worker envelopes for Apollo catalog rows"). No verification is implied by this note. Reopen with `sase bead open sase-xe.16.11.5`, or pass `-B|--do-not-close-bead` on mid-flight commits.

[2026-09-09T16:14:31Z · sase-xe.16.11.land] LAND AUDIT: Reopened after automatic-close note #8 because note #4 explicitly leaves receipt/launch visibility/TUI output/stop unmet; note #3 only proves unavailable content on a stale row. b7c6bc006 improves real envelope traversal, legal requests, basic metadata and canonical project alias resolution, but proposals #5-#7 are required epic work. Fresh audit probes: payload.freshness.partial=True projects partial=False; summary.observed_at_unix=1800000000 projects fleet_observed_at_unix=None; one followed DONE row with host-wide counts.running=9 projects Focus remote running=9; raw worker host objects still fail the Rust count schema on alias and are silently swallowed. Gateway batch_lookup confirms counts are host-wide. catalog_next_cursor chooses one host cursor and _fetch_fleet_catalog broadcasts it to all hosts with a hard three-page stop. Preserve the successful Serve/init/hello evidence from #1-#2, but require matching published builds and same-session live launch receipt, fresh visibility, known recent DONE, follow/output/stop and gateway restart recovery before normal close. The remaining-work child plan owns all repairs; do not create standalone debt for these proposals.

## Dependencies

- **Depends on:** [sase-xe.16.11.4](sase-xe.16.11.4.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.5/README.md) | [sase-xe.16.11.5](sase-xe.16.11.5.md) | 1 |
| [bbugyi200.athena.toobig-52.machine\_init.0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.toobig-52.machine_init.0.md) | [sase-xe.16.11.5](sase-xe.16.11.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b7c6bc0`](https://github.com/sase-org/sase/commit/b7c6bc0067032b53f30e841b54a6f179d4ff52e1) | fix(ace): decode live Fleet worker envelopes for Apollo catalog rows | [sase-xe.16.11.5](sase-xe.16.11.5.md) | 2026-09-09 11:59:41 EDT |
| sase | [`54b1d07`](https://github.com/sase-org/sase/commit/54b1d07a4ca2bdefb15cb2fecfb0e34ed892ced5) | refactor(dispatch): split machine init helpers | [sase-xe.16.11.5](sase-xe.16.11.5.md) | 2026-09-09 12:48:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.1p.final][1] | Record the live Apollo acceptance gate that must not pass with empty Fleet or broken Focus | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.1p.final/README.md

<!-- sase:referenced-by:end -->
