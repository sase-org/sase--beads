# Bead: sase-1s5.1 — Terminal-blocked wait notices name their waiter, and the silent-waiter case is reproduced and closed

[Bead Pages](../README.md) / [sase-1s5](README.md) / sase-1s5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cy--6` · **Assignee:** `sase-1s5.1` · **Size:** medium
**Created:** 2026-11-08 06:51:28 EST · **Closed:** 2026-11-08 07:24:16 EST
**Plan:** [202611/health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/health_watch_fixes.md)

## Description

wait-notice-fixes: resolve the Waiter label from the waiter's agent_meta.json instead of waiting.json's cl_name (F8), then reproduce the athena sase-1ra.7 session shape (failed root turn plus failed staged monitor) in a wait_checks test and fix wherever its terminal blocker is dropped (F9).

## Notes

[2026-11-08T12:24:16Z · sase-1s5.1] F8: Waiter label now resolves from waiter agent_meta.json name with dir-name fallback, never cl_name; terminal blockers carry blocker agent name (Blocked on dep (member): dir (outcome)). F9: fixed mixed agent+bead skip so agent blocker with same string as closed bead still notifies; added sase-1ra.7 fixture (failed root+failed monitor) plus dropped-followup variant. Verified: 24 terminal-outcome tests pass, 12 epic-follow safety pass, 211 wait-dependency tests pass, sase tool run check fcc55ced verdict pass.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s5.1/README.md) | [sase-1s5.1](sase-1s5.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1s5.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s5.1/README.md

<!-- sase:referenced-by:end -->
