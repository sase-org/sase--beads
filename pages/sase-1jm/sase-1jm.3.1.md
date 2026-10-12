# Bead: sase-1jm.3.1 — Implement the read-only Agents Archive view for sase-1jm.3

[Bead Pages](../README.md) / [sase-1jm.3](sase-1jm.3.md) / sase-1jm.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.land`
**Created:** 2026-10-10 20:21:20 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/agents_archive_view_phase.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 7 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md

<!-- sase:links:end -->

## Description

The Agents tab can browse this machine's dismissed runs through a beta-flagged Archive view, preserve each view's state, and render retained decks without restoring runs or disturbing Inbox state.

## Notes

[2026-10-11T23:12:48Z · sase-1jm.3.1.land] LAND TRIAGE (2026-10-11, master d289b664a6) of every PROPOSED FOLLOW-UP: (1) 3.1.1#2 symvision KNOWN unused publics -> declined, resolved by 1517ed288f; symvision is now red only for the unrelated stale 'sase-1jx.6(classify_project_candidates)' entry, recorded as DISCOVERED ISSUE on sase-1jx. (2) 3.1.2#1 corpus-facade JSON serialization -> declined, tests/core/test_agent_archive_corpus_facade.py passes now. (3) 3.1.3#3, 3.1.5#1, sase-1jm.3#5, sase-1jm#1 clean-base failures -> completion snapshot x2, flag candidates, and bob dry-run now pass (c10f074f59), declined as resolved; marker audit now fails only on run_agent_wait_deps.py:_scoped_project_rows from d289b664a6 -> DISCOVERED ISSUE on sase-1jy (older sites tracked by sase-1by); import budget 3516 vs <3513 -> tools/tui_import_closure --diff 69f647d912^ attributes +2 to this epic (actions.agents._archive_view, models.agent_archive_view), which is remaining epic work; the pre-epic excess (base 3514) was +1'd on sase-1ic. Load flakes: new flake beads sase-1k1 (test_full_cluster_reads_label_chip_separator_label_chip), sase-1k2 (test_provider_drain_e2e_relaunches_stranded_agent), sase-1k3 (test_supervisor_sigterm_records_stop_intent_worker_settles_stop). (4) 3.1.5#2 import cap -> same as (3). (5) 3.1.6#3 -> import budget as (3); flakes +1'd on sase-120 (sdd git identity) and sase-19c (inline caller group sigkill), plus new sase-1k0 (test_watchdog_stops_unjoined_run_when_starter_dies). (6) 3.1.7#1 stuck 'Loading archived run…' placeholder -> epic-caused, remaining epic work. (7) 3.1.7#2 Archive j/k p95 confirmation -> remaining epic proof work, not a task. (8) 3.1.7#4 missing_index golden flake -> epic-caused (the Archive info row pads the right-aligned ',a Inbox' from the pre-layout self.size.width), remaining epic work. (9) sase-1jm.3#1-#3 glossary -> declined here: these are addressed to the sase-1jm parent land agent under glossary_archive_term=no and glossary_strand_updates=no, so they stay on sase-1jm.3. (10) sase-1jm.3#4 agents_unified_query matrix -> declined: the flag was retired by b46ecb0a94 before this epic, so no legacy editor path remains to test.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.land.md) | [sase-1jm.3.1](sase-1jm.3.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.1][1] | Need child epic scope and decisions | 1 |
| read-by | [agent:sase-1jm.3.1.2][2] | Need sibling phases so unused controller APIs can be re-keyed | 1 |
| read-by | [agent:sase-1jm.3.1.3][3] | Need epic decisions | 1 |
| read-by | [agent:sase-1jm.3.1.4][4] | Need the child epic's final decisions and shared contracts before implementing its assigned phase | 1 |
| read-by | [agent:sase-1jm.3.1.5][5] | Need parent epic decisions and recorded contracts | 1 |
| read-by | [agent:sase-1jm.3.1.6][6] | Need epic DECISIONS and scope | 1 |
| read-by | [agent:sase-1jm.4][7] | Need child-epic structure precedent for decomposing sase-1jm.4 | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.5/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.6/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4/README.md

<!-- sase:referenced-by:end -->
