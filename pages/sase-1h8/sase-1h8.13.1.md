# Bead: sase-1h8.13.1 — Finish read-model mutations so sase-1h8.13 can close

[Bead Pages](../README.md) / [sase-1h8.13](sase-1h8.13.md) / sase-1h8.13.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.land`
**Created:** 2026-10-08 14:46:03 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_read_model_mutations_child_epic.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 8 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md

<!-- sase:links:end -->

## Description

Every ordinary bead mutation runs one shared algorithm on an indexed mutation view. On a warm cache it loads only the rows and streams it affects. It writes its delta through to the read model inside the same beads.db critical section, with no second sweep and no full-snapshot load. Randomized parity shows cache equals full replay after every operation. Matched 1x/8x note/update evidence is recorded. sase-1h8.13 then closes and the waiting acceptance gate sase-1h8.14 can start. Phase planners also stop re-planning a phase that was left unfinished as another single-agent tale.

## Notes

[2026-10-09T01:16:28Z · sase-1h8.13.1.land] Land triage of phase PROPOSED FOLLOW-UPs (2026-10-08): (1) sase-1h8.13.1.3 #1, sase_gateway sudo_runner timeout_terminates_process_group_and_records_failed_entry failing under the full sase-core check (worker.rs:24 result.is_ok(); passes alone; not caused by this epic). Corroborated existing flake sase-15h with +1: same Fixture::new write-then-exec fake-sudo path, and the hidden Err text is noted. (2) sase-1h8.13.1.4 #1, provider_priority concurrent_priority_changes_and_auto_disables_are_serialized LockTimeout under the full lane, passes alone; not caused by this epic. Corroborated existing task sase-yn with +1, with run ed620c99 evidence and a pass-alone observation. (3) sase-1h8.13.1.7 #1, 1x->8x p95 ratio 2.8-2.9x misses the parent's <10% target. This is the parent epic's own acceptance target, owned by perf gate sase-1h8.14, so it was routed as a DISCOVERED ISSUE note on active epic sase-1h8 with both artifacts. No task was created. (4) sase-1h8.13.1.8 #1, symvision 48 unused publics; pre-existing and tracked by sase-1hp. Declined as a new task: 'just symvision' is green on master d0b6e2e99d (likely fixed by 1fedb63427), and a status note was added to sase-1hp.

[2026-10-09T01:19:59Z · sase-1h8.13.1.land] Land verification (2026-10-08, sase-core 3e459248, sase d0b6e2e99d): NOT closing yet. All 8 phases are closed and committed (sase-core 64605819, 906570e8, 159f48ef, 276b14a4, d18537a5, dd1a67c0, 3e459248; sase c64a6b3ea7). Direct write-through, the content-generation CAS, the forced-sweep fix, affected-row cached paths for every family, the warm-path/proof suites and the matched bench are real. epic-symbols are clean; there is no double-append (cached declines happen only before any durable write); bead_read_parity has no conflict with the parallel fix e411a392. Unmet deliverables: (a) No single algorithm. Every entry point keeps its MutableStore::load replay copy next to a hand-mirrored try_cached_* copy, the view's replay backing is test-only under #[allow(dead_code)], there is no view-owned event staging or commit, and minting exists twice. Mutation modules grew from ~3.2k to ~6.85k lines. This contradicts the epic goal and the view-core and port phase specs. (b) The dual-mode phase added 10 new tests instead of running the 9 existing suites (151 tests) in both modes; those tests still never create .git, so sase-1h8.13's 'every existing mutation test passes in both modes' is unmet. Drift: publish-direct grew the over-cap read_model/store.rs from 2099 to 2174 lines and tail.rs from 1519 to 1554 against the epic rule; docs/beads.md's 'phase agent auto-approves an epic-tier plan' went stale after e6adb110af (%auto:tale). Remaining work proposed as a child epic (parent_bead sase-1h8.13.1) with phases suite-modes, replay-goldens, view-commit, unify-lifecycle, unify-claims-deps, unify-links-evidence, caps-docs and proof. Its land agent resumes this landing.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.13.1.land.md) | [sase-1h8.13.1](sase-1h8.13.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.1][1] | parent epic scope and DECISIONS | 1 |
| read-by | [agent:sase-1h8.13.1.2][2] | parent epic scope | 1 |
| read-by | [agent:sase-1h8.13.1.3][3] | Need parent epic scope and decisions | 1 |
| read-by | [agent:sase-1h8.13.1.4][4] | parent epic context | 1 |
| read-by | [agent:sase-1h8.13.1.5][5] | epic decisions | 3 |
| read-by | [agent:sase-1h8.13.1.6][6] | Need parent epic scope and DECISIONS | 1 |
| read-by | [agent:sase-1h8.13.1.7][7] | epic decisions for proof phase | 2 |
| read-by | [agent:sase-1h8.13.1.9.4][8] | landing notes and prior epic context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.5/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.6/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.7/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.9.4/README.md

<!-- sase:referenced-by:end -->
