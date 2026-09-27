# Bead: sase-1aq.10.4 — Prove and land deployed owner-to-viewer Agents parity

[Bead Pages](../README.md) / [sase-1aq.10](sase-1aq.10.md) / sase-1aq.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.23](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.23.md) · **Assignee:** `sase-1aq.10.4` · **Size:** medium
**Created:** 2026-09-26 17:34:44 EDT · **Closed:** 2026-09-26 19:15:18 EDT
**Plan:** [202609/finish\_1aq\_live\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_1aq_live_closeout.md)

## Description

parity_landing: complete the production parity oracle and same-build live captures, then land sase-133.5 and sase-133.

## Notes

[2026-09-26T23:14:41Z · sase-1aq.10.4] PROPOSED FOLLOW-UP: same-build settled owner (apollo) + viewer (athena machine:apollo) Agents captures at identical geometry, then normal land of sase-133.5.4, sase-133.5 and sase-133 — owner: sase-133.5.land / sase-133.land (installed sase differs: apollo 0.17.1+1549 dirty vs athena 0.17.1+1540; needs normal update flow + gateway/AXE restart outside an agent turn)

[2026-09-26T23:14:55Z · sase-1aq.10.4] PROPOSED FOLLOW-UP: test_fleet_agents_display_parity.py::test_project_fleet_agents_render_like_local_rows_modulo_host_chip fails on clean base (AttributeError AgentType.PROC_SHELL after shell-to-turn rename) — tracked under sase-th red-master repairs; oracle files pass (facts 32, roster 1)

[2026-09-26T23:15:18Z · sase-1aq.10.4] parity_landing verified 2026-09-26T~23:15Z: production oracle green (test_owner_facts_oracle 32 passed, test_owner_roster_oracle 1 passed; family_anchor + lifecycle_evidence present in linked sase-core); live version diagnostics clean (apollo hello ok, gateway 0.34.73, fleet schema v6, no false skew, both hosts core 0.34.73+46); sase bead epic-symbols clean; no repo files changed. Same-build settled captures + normal land of sase-133.5.4/.5/sase-133 handed to sase-133.5.land/sase-133.land via PROPOSED FOLLOW-UP (installed sase builds differ across hosts). One clean-base failure (display_parity PROC_SHELL rename fallout) recorded as PROPOSED FOLLOW-UP under sase-th.

## Dependencies

- **Depends on:** [sase-1aq.10.3](sase-1aq.10.3.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.10.5](sase-1aq.10.5.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.4/README.md) | [sase-1aq.10.4](sase-1aq.10.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1aq.10.5][1] | publish_memory must verify parity landing claims | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.5/README.md

<!-- sase:referenced-by:end -->
