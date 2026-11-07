# Bead: sase-1qz.11 — Remove the flag, document, and prove it end to end

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.11` · **Size:** medium
**Created:** 2026-11-02 17:42:18 EST · **Closed:** 2026-11-07 04:14:45 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

land: run an end-to-end hijack-and-escalate test across primary and linked repos, delete the agent_hijack flag's Off branch and close its bead, update the reference docs, and publish the glossary strand and decision records per the memory decisions.

## Notes

[2026-11-06T22:34:13Z · sase-1qz.11] PROPOSED FOLLOW-UP: Telegram and mobile recovery — let an authorized remote user inspect and answer unresolved hijack recovery actions; current phase delivers the TUI and CLI paths.

[2026-11-06T22:34:18Z · sase-1qz.11] PROPOSED FOLLOW-UP: Quiet-time stall hint — show a read-only “quiet for N minutes” hint without automatically changing agent lifecycle state.

[2026-11-06T22:34:23Z · sase-1qz.11] PROPOSED FOLLOW-UP: Revisit x-as-fate-chooser — assess whether the key should select a terminal recovery action or keep the current explicit mapping.

[2026-11-06T22:34:29Z · sase-1qz.11] PROPOSED FOLLOW-UP: Hijack expiry warning — notify before the held workspace claim expires, using hijacked_at-based age.

[2026-11-06T22:34:35Z · sase-1qz.11] PROPOSED FOLLOW-UP: Salvage & Commit — evaluate a recovery action that commits hijacked work before releasing the workspace.

[2026-11-06T22:34:41Z · sase-1qz.11] PROPOSED FOLLOW-UP: Decision records — reconsider publishing the never-downgrade and held-custody decisions after reviewer selected decision_records=no for this land phase.

[2026-11-06T22:34:46Z · sase-1qz.11] PROPOSED FOLLOW-UP: Recovery guide candidate — decide whether hijack recovery merits a user guide once its steps are stable; the current interrupted-agent guide remains accurate.

[2026-11-06T22:37:41Z · sase-1qz.11] PROPOSED FOLLOW-UP: Reconcile the linked sase-core schema before `sase tool run check` — setup stops at `agent_artifact_run_trash_wire_schema_version` (got 2, expected 1), matching the failure already recorded on sase-1qz.9 note #1 and the stale-core follow-up in sase-1gu.6 note #1.

[2026-11-07T09:14:45Z · sase-1qz.11--1] Removed the agent_hijack Off branch and registry/schema entry, regenerated reference docs and the authorized glossary strand, and closed flag bead sase-1r1 per the answered gate. The focused stop, TUI ingress, and fakey end-to-end tests pass (19 passed); the feature flag integrity check and epic-symbol check are clean. The named repository check is blocked in setup by the linked sase-core schema mismatch (agent_artifact_run_trash_wire_schema_version: got 2, expected 1), already tracked by sase-1gu.6 and this phase follow-up.

## Dependencies

- **Depends on:** [sase-1qz.10](sase-1qz.10.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1qz.5](sase-1qz.5.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.11.md) | [sase-1qz.11](sase-1qz.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18n][1] | Check in-progress hijack phase notes for deviations from the plan, for a user-facing report | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |
| read-by | [agent:sase-1qz.11--1][3] | Need the phase scope, design file, and prior work status | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.18n/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.11.md

<!-- sase:referenced-by:end -->
