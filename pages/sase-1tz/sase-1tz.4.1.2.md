# Bead: sase-1tz.4.1.2 — Serve cached fleet snapshots stale-while-revalidate in the gateway

[Bead Pages](../README.md) / [sase-1tz.4.1](sase-1tz.4.1.md) / sase-1tz.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.4.md) · **Assignee:** `sase-1tz.4.1.2` · **Size:** medium
**Created:** 2026-11-20 14:00:21 EST · **Closed:** 2026-11-20 17:10:45 EST
**Plan:** [202611/hygiene\_gateway\_notifications\_retention.md](https://github.com/sase-org/sase--plans/blob/main/202611/hygiene_gateway_notifications_retention.md)

## Description

gateway_swr: an expired cached snapshot is served at once, marked stale, while one background rebuild runs. Index-permit waits are bounded. A cold cache keeps today's bounded wait. Record the relationship on sase-1s5 and move the pin.

## Notes

[2026-11-20T20:44:50Z · sase-1tz.4.1.2] Baseline (read-only, 2026-11-20): Apollo gateway output.log retained 2026-11-14T13:05:59Z through 2026-11-20T20:27:59Z (about 6d 7h, short of the requested 7d): 6,480 presentation builds, 3 over 60s, maximum 1,796,293ms (29m56s), 137 timed-out waiters across 84 builds, and 5 HTTP 504 responses. Athena gateway output.log was empty (mtime Sep 20), so its before counts are unavailable. After-install comparison command: `ssh <host> 'rg "fleet snapshot build finished|Status code: 504 Gateway Timeout" ~/.sase/service/procs/gateway/output.log'` on each host. PROPOSED FOLLOW-UP: preserve a durable seven-day gateway log or metric source on Athena and rerun its before measurement; the current gateway output.log is empty.

[2026-11-20T21:29:18Z · sase-1tz.4.1.2] PROPOSED FOLLOW-UP: refresh tests/completion/snapshots/cli_spec.json for the current argparse tree; both snapshot tests fail identically on the clean base (witness 6d36d121952c954cfad879804e439942, repeat of known drift) after the earlier sase-1om fix, and no active bead tracks this recurrence.

[2026-11-20T22:10:45Z · sase-1tz.4.1.2] Implemented and documented stale-while-revalidate serving for cached fleet snapshots with a five-minute immediate stale window, one background rebuild, and bounded index-permit waits; cold and forced refresh paths retain bounded waits. Verified 33 Rust fleet-read tests and 6 focused TUI tests pass, and linked sase-core check passes. The SASE check reports only the two CLI completion snapshot drift tests, reproduced on the clean base and recorded as a proposed follow-up. Recorded baseline measurements, the sase-1s5 relationship, and the core revision pin update.

## Dependencies

- **Depends on:** [sase-1tz.4.1.1](sase-1tz.4.1.1.md) ✓ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.2/README.md) | [sase-1tz.4.1.2](sase-1tz.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a3b95da`](https://github.com/sase-org/sase-core/commit/a3b95da517ac4ea36267de9da869070397c66c46) | feat(gateway): serve stale fleet snapshots while rebuilding | [sase-1tz.4.1.2](sase-1tz.4.1.2.md) | 2026-11-20 17:13:06 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.4.1.2][1] | Verify the gateway phase note and assigned status before final close | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.4.1.2/README.md

<!-- sase:referenced-by:end -->
