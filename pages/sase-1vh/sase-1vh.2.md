# Bead: sase-1vh.2 — Typed host lookup failures, provider-retry exclusion, honest runner hint

[Bead Pages](../README.md) / [sase-1vh](README.md) / sase-1vh.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gu](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gu.md) · **Assignee:** `sase-1vh.2` · **Size:** small
**Created:** 2026-11-26 14:45:31 EST · **Closed:** 2026-11-26 15:43:12 EST
**Plan:** [202611/launch\_lookup\_busy\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202611/launch_lookup_busy_resilience.md)

## Description

typed-transient-classification: add an IndexLookupUnavailable base with a transient flag for both lookup exceptions, exclude host lookup failures from provider retry via is_host_owned_failure, and make record_runner_error print a typed transient or index-repair hint instead of the coincidental provider match.

## Notes

[2026-11-26T20:43:12Z · sase-1vh.2] Implemented typed IndexLookupUnavailable failures, excluded host lookup errors from provider retries, added honest runner hints, and verified focused tests (10 passed). just check passed all lint gates but its 63,754-test scoped lane had two unrelated failures and one TUI settle timeout; all three failed cases passed individually on the clean base tree.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vh.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.2/README.md) | [sase-1vh.2](sase-1vh.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6574797`](https://github.com/sase-org/sase/commit/6574797e4031905e18c8cdcbf9118cb6552d3c23) | fix(agent-retry): classify host index lookup failures | [sase-1vh.2](sase-1vh.2.md) | 2026-11-26 15:44:58 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vh.2][1] | Need the phase scope, design file, decisions, and prior work notes before implementation | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vh.2/README.md

<!-- sase:referenced-by:end -->
