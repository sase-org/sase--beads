# Bead: sase-1nf.11 — Drain the publication backlog on athena and apollo in bounded batches

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.11

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.11` · **Size:** medium
**Created:** 2026-10-20 13:36:15 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1nj][1] | Dud rows consume the bounded drain budget this phase will spend |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1nj/README.md

<!-- sase:links:end -->

## Description

pub-recover: on both hosts, back up unique unpublished content, retry quarantined requests in bounded batches while verifying remote publication and a falling backlog, confirm new agents publish, and close sase-10x.

## Notes

[2026-10-22T12:45:27Z · sase-1nf.10.1.9.1.6.land] DISCOVERED ISSUE / handoff from the sase-1nf.10.1.9.1.6 landing. This covers sase-1nf.10.1.9.1.6.4 PROPOSED FOLLOW-UP #2: retry apollo/sase manifest_mismatch once push works. The class has never been reached. Its limit-1 canary selected active row 9t--4--review@5d212ef964b, and the push was denied. Bounded commands are in research:202610/publication_recovery_acceptance.md. Apollo write access was NOT lost (re-diagnosed in sase-1ni): pushes fail only when an agent runs Apollo commands over 'ssh apollo' with Athena's forwarded agent, which offers the bobs-org/bob deploy key first. Before any Apollo drain: fix sase-1ni, or run with 'ssh -o ForwardAgent=no apollo ...', and confirm 'ssh -T git@github.com' greets bbugyi200. Clean stranded commits a090a3a2c (bob-cli--agents) and f2d32a476b (sase--agents) are still ahead 1 on Apollo as of 2026-10-22 ~12:40Z and should push on the next normal drain. Also expect stale-revision dud worker rows (sase-1nj) to win active-first selection on athena/sase.

## Dependencies

- **Depends on:** [sase-1nf.10](sase-1nf.10.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.11/README.md) | [sase-1nf.11](sase-1nf.11.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.land][1] | Check existing owners for proposed follow-ups (TUI import budget, bulk drain backlog) | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.land/README.md

<!-- sase:referenced-by:end -->
