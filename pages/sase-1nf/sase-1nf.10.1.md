# Bead: sase-1nf.10.1 — Make publication drains bounded and recoverable

[Bead Pages](../README.md) / [sase-1nf.10](sase-1nf.10.md) / sase-1nf.10.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.land`
**Created:** 2026-10-20 15:40:51 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/publication_drain_fixes.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 8 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md

<!-- sase:links:end -->

## Description

Fix the measured publication failures and prove safe recovery before bulk backlog draining

## Notes

[2026-10-20T23:47:26Z · 9n--3] DISCOVERED ISSUE during conflict repair on paused base fe45b86f28: required sase tool run check e5ef36a8a683509a2f1174167a8eac6d exited 1 at Symvision because all five --epic-symbol entries for sase-1nf.10.1.3 now name a closed phase (closed 2026-10-20T23:42:10Z). The repair changes tests only; Justfile and the entire src tree match HEAD exactly. All earlier check stages passed. The phase close note says its landing cleaned the epic-symbols, so this is a frozen rebase base observing a newer external bead status; please preserve the cleanup in the epic landing. No out-of-scope whitelist edits were included in the repair.

[2026-10-20T23:52:55Z · toobig-8c.test_deck_split_pilot.0] INDEPENDENT REPRODUCTION (2026-10-20): this workspace's just _lint-symvision and final sase tool run check f7aea2cddb7ed22548a3aa728a0468d0 fail on the same five --epic-symbol flags for closed phase sase-1nf.10.1.3 (closed 2026-10-20T23:42:10Z); check stops before tests. The deck split and focused tests pass, and no Justfile or src changes are in the split diff.

[2026-10-22T12:41:24Z · sase-1nf.10.1.9.1.6.land] DISCOVERED ISSUE (from sase-1nf.10.1.9.1.6.3 PROPOSED FOLLOW-UP #1, triaged by the sase-1nf.10.1.9.1.6 land agent): the backup-first stale-replay helper built in sase-1nf.10.1.8 persists stale refusal metadata. Root cause: src/sase/agents_sync/_publication_replay_recovery_backup.py ensure_backup() returns early when the existing progress.json stage is verified/mutation/complete, so a re-report recomputes refused_same_run_divergences() fresh (and reports zero refusals) but never rewrites progress['refused']. Once apply enters a MUTATION_STAGE, _publication_replay_recovery_recover.py resumes from progress.get('refused') instead. Production impact on 2026-10-22: the preserved sase-1nf.10.1.9.1.1 backup re-reported verified with no refusals under the new merge-base policy; apply reset/replayed and committed, the push failed (deploy-key identity, see the SSH task filed from .6.4), and resume was then refused on five stale old-policy refusals. Recovery finished safely with a new backup (/home/bryan/.sase/recovery-backups/bob-cli-replay-sase-1nf.10.1.9.1.6.3). Fix direction: refresh (or refuse on disagreement with) stored refusals when a verified pre-mutation backup is re-reported, and add an interrupted-push/resume fixture to tests/agents_sync/test_publication_replay_recovery.py. Evidence: file:explicit:0a2f73e51e5d9337c3710d44.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.land/README.md) | [sase-1nf.10.1](sase-1nf.10.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:9n--3][1] | Confirm active ownership of the closed-phase Symvision exclusions blocking required rebase verification | 1 |
| read-by | [agent:sase-1nf.10.1.1][2] | Need later-phase consumers so unused facade APIs can be epic-symbol keyed to still-open beads | 2 |
| read-by | [agent:sase-1nf.10.1.2][3] | Need the epic decisions governing this phase | 1 |
| read-by | [agent:sase-1nf.10.1.3][4] | Need epic DECISIONS for phase work | 1 |
| read-by | [agent:sase-1nf.10.1.5][5] | Need epic DECISIONS | 1 |
| read-by | [agent:sase-1nf.10.1.6][6] | Need parent scopes and epic decisions for this phase | 1 |
| read-by | [agent:sase-1nf.10.1.7--2][7] | Check whether the stale sibling epic-symbol lint failure is already tracked by the parent epic | 1 |
| read-by | [agent:toobig-8c.test_deck_split_pilot.0][8] | Confirm the in-progress publication-drain epic's responsibility for the closed-phase whitelist entries before routing the lint finding | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.9n.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.3/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.5/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.6/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.7.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-8c.test_deck_split_pilot.0/README.md

<!-- sase:referenced-by:end -->
