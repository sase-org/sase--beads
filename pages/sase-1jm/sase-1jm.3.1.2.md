# Bead: sase-1jm.3.1.2 — Off-thread Archive loading, prewarm, and revalidation

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.2` · **Size:** medium
**Created:** 2026-10-10 20:21:21 EDT · **Closed:** 2026-10-10 23:04:57 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

corpus-controller: add a coalesced Archive controller around the existing core corpus cache and summary, rows, lookup, and count methods. Build and query off-thread, publish only current generations, gate prewarm on the first complete Inbox load and idle UI, and revalidate index and link signatures without archive scans on idle ticks. Preserve selection and page requests across rebuilds. Test cold, warm, missing, rebuilding, and stale-result paths.

## Notes

[2026-10-11T03:04:42Z · sase-1jm.3.1.2] PROPOSED FOLLOW-UP: KNOWN just check reds on clean-base corpus facade JSON serialization (AgentArchiveCorpusHandle not JSON serializable in tests/core/test_agent_archive_corpus_facade.py) plus unused-public cache/geometry/history symbols (sase-1jp tracks project_for_done); sase tool run 10264287633d700bf2eece8cffb6759d verdict no_new_failures

[2026-10-11T03:04:57Z · sase-1jm.3.1.2] Verified off-thread last-request-wins Archive corpus controller: Inbox-complete+idle prewarm, cheap idle tokens, missing/unreadable/rebuilding paths, selection preserve, lookup, cancel-on-unmount. 32 controller+foundation tests passed. sase bead epic-symbols sase-1jm.3.1.2 had no leftovers (later-phase snapshot/pulse/windows/lookup allowlisted on sase-1jm.3.1.3 and sase-1jm.3.1). sase tool run check 10264287633d700bf2eece8cffb6759d: no_new_failures (23 KNOWN).

## Dependencies

- **Depends on:** [sase-1jm.3.1.1](sase-1jm.3.1.1.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.3.1.3](sase-1jm.3.1.3.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.2/README.md) | [sase-1jm.3.1.2](sase-1jm.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`254d93c`](https://github.com/sase-org/sase/commit/254d93cc5808b7f12850027883a7be86c64ef195) | feat(tui): add pump-free Archive corpus controller | [sase-1jm.3.1.2](sase-1jm.3.1.2.md) | 2026-10-10 23:06:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.2][1] | Need remaining phase scope, later-phase seams, and notes before closing | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.2/README.md

<!-- sase:referenced-by:end -->
