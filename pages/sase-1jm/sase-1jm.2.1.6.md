# Bead: sase-1jm.2.1.6 — sase agent search parity and the bench

[Bead Pages](../README.md) / [sase-1jm.2.1](sase-1jm.2.1.md) / sase-1jm.2.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.md) · **Assignee:** `sase-1jm.2.1.6` · **Size:** medium
**Created:** 2026-10-10 07:31:49 EDT · **Closed:** 2026-10-10 16:03:36 EDT
**Plan:** [202610/archive\_corpus.md](https://github.com/sase-org/sase--plans/blob/main/202610/archive_corpus.md)

## Description

cli-parity: route in:archive and in:inbox through the corpus and catalog, and prove CLI order matches rows().

## Notes

[2026-10-10T19:58:44Z · sase-1jm.2.1.6--1] Archive corpus benchmark (synthetic 11,000 top-level rows + 37,000 workflow children, 7 samples): build p95=1696.8ms (target <300ms); query + first window p95=2730.6ms (target <30ms). The benchmark failed its budgets. PROPOSED FOLLOW-UP: optimize archive compilation and query/window transport to meet both latency budgets while preserving correct restorable checks and corpus ordering.

[2026-10-10T20:03:23Z · sase-1jm.2.1.6--1] PROPOSED FOLLOW-UP: The sase tool run check feature-flag lint fails identically on clean base f7026aa2f2 with four closed flag definitions still present (sase-1gw claude_helper_channel, sase-1gv grok_rules_delivery, sase-1h4 instruction_shadow_render, sase-178 muse_synchronous_shell). The cleanup is already scoped to phase sase-1jc.10; this check failure is pre-existing and did not come from this phase.

[2026-10-10T20:03:36Z · sase-1jm.2.1.6--1] Verified archive CLI parity focused suite: 17 passed; recorded synthetic corpus p95 measurements and latency follow-up on the bead. sase tool run check passed format/Ruff/mypy but stopped at feature-flag lint; reproduced the identical four closed-flag failures on clean base f7026aa2f2 and recorded the existing owner phase. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1jm.2.1.5](sase-1jm.2.1.5.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.2.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.6.md) | [sase-1jm.2.1.6](sase-1jm.2.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5f47d11`](https://github.com/sase-org/sase/commit/5f47d119356f02a87ec850aba52c6bd5090bd365) | feat(agents): add archive search CLI parity | [sase-1jm.2.1.6](sase-1jm.2.1.6.md) | 2026-10-10 16:04:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.2.1.6--1][1] | Verify the phase is closed with benchmark and base-check evidence recorded | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.1.6.md

<!-- sase:referenced-by:end -->
