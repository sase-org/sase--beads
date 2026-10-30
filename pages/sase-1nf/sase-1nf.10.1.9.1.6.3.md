# Bead: sase-1nf.10.1.9.1.6.3 — Install the fixes on both hosts and recover Apollo bob-cli content

[Bead Pages](../README.md) / [sase-1nf.10.1.9.1.6](sase-1nf.10.1.9.1.6.md) / sase-1nf.10.1.9.1.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10.1.9.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.1.land.md) · **Assignee:** `sase-1nf.10.1.9.1.6.3` · **Size:** medium
**Created:** 2026-10-21 10:45:31 EDT · **Closed:** 2026-10-22 07:11:55 EDT
**Plan:** [202610/publication\_blockers\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_blockers_acceptance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:0a2f73e51e5d9337c3710d44 | attached via sase artifact create --bead |
| related | file:explicit:2b39984b614454d0fad35467 | attached via sase artifact create --bead |
| related | file:explicit:4b8203965ca7b80abdbb6cd4 | attached via sase artifact create --bead |
| related | file:explicit:6bb0a3bad7880c345c167024 | attached via sase artifact create --bead |
| related | file:explicit:6f0d4aa7c4fb0eb6a8ca3113 | attached via sase artifact create --bead |
| related | file:explicit:9f2c23a8b3d9bd53371c40ad | attached via sase artifact create --bead |
| related | file:explicit:f1176d53bef9cf9cc67f3d1d | attached via sase artifact create --bead |
| related | file:explicit:f3ae6ce054168755bc7f3a4a | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

install-replay: confirm both fixes landed, gate sase update on athena and apollo, then run the backup-first replay report, apply, and repeat apply on Apollo bob-cli with content and remote proof.

## Notes

[2026-10-22T11:11:33Z · sase-1nf.10.1.9.1.6.3--1] PROPOSED FOLLOW-UP: Refresh stale refusal metadata when a verified backup is re-reported after policy changes or an interrupted push — the prior backup retained five refusals and blocked resume after its first push failed; add an interrupted-push/resume fixture. This phase completed safely with a new backup.

[2026-10-22T11:11:55Z · sase-1nf.10.1.9.1.6.3--1] Verified Athena and Apollo load SASE ba7ab4e96bce13fdf71b9e429bffe92a8cf39205 and core 1503d604844a32a8a93e944addabb0887f8d9bc4. On Apollo, backup-first report passed; replay apply published commit 3733feaf2a5e1fd2341e5df92705a986045de8a5; repeat apply returned already_complete with ahead=0 and behind=0. Fetched remote main 650c73595a6b452aa168f567538f120d8cd4d319 contains replay and validates all 3 manifests/804 snapshots, target-run payload hashes, completed states, prompt steps, large monitor chats, archive objects, and all 6,426 pre-existing upstream-only paths unchanged. Attached raw version, revision, replay, scoped inventory, remote proof, outbox, and phase-summary artifacts. Recorded the stale refusal metadata recovery follow-up.

## Dependencies

- **Depends on:** [sase-1nf.10.1.9.1.6.1](sase-1nf.10.1.9.1.6.1.md) ✓ · ⧖ 2026-10-21
- **Depends on:** [sase-1nf.10.1.9.1.6.2](sase-1nf.10.1.9.1.6.2.md) ✓ · ⧖ 2026-10-21
- **Blocks:** [sase-1nf.10.1.9.1.6.4](sase-1nf.10.1.9.1.6.4.md) ✓ · ⧖ 2026-10-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.9.1.6.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.1.6.3.md) | [sase-1nf.10.1.9.1.6.3](sase-1nf.10.1.9.1.6.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.9.1.6.5][1] | Review the parent epic, phase evidence, and remaining acceptance scope before doing acceptance work | 1 |
| read-by | [agent:sase-1nf.10.1.9.1.6.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.9.1.6.land/README.md

<!-- sase:referenced-by:end -->
