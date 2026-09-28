# Bead: sase-1bu.6 — The goal artifact kind and @goal citations

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.6` · **Size:** medium
**Created:** 2026-09-27 19:03:26 EDT · **Closed:** 2026-09-28 04:11:59 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

artifact-kind: make goal: a first-class builtin artifact kind across the sase-core catalog, parser, resolver, and editor/LSP kind lists. Wire it through Python builtin-entry dispatch, artifact read/show/path, one-line @goal prompt expansion, staging, and ACE @goal payload completion, with zero golden churn.

## Notes

[2026-09-28T08:10:51Z · sase-1bu.6] PROPOSED FOLLOW-UP: tests/doctor/test_checks_beads.py::test_project_beads_skips_when_store_is_absent fails on this host because pre-existing /home/bryan/sdd/beads (Sep 26) is found by the parent-walk discovery; fails identically on the clean base tree, unrelated to artifact-kind

[2026-09-28T08:11:59Z · sase-1bu.6] goal: is a first-class builtin kind end to end. sase-core: Goal kind/payload wire, parse/render/resolve via goal ids, fragments rejected, catalog+reserved+editor lists, none-path, goal/render markdown (card+citation<=400ch) with 3 new bindings (goal_card_view/markdown/citation_line). sase: mirrors, builtin_entry_goal (id/status/title/outcome, missing+unknown_project diagnostics), read card/show/path items-dir/open pages card, @goal expansion, staging, ACE payload rows from hot projection + [⌖] #FF87AF badge + goal: goals title, docs. Verified: sase-core sase tool run check green; sase lint gates all green incl symvision (dropped now-used sase-1bu goal_ledger_show+resolve_goal_ledger entries); 37 visual goldens unchanged; new tests/goals/test_goal_artifact_kind.py (16) + Rust kind/render/scanner/binding tests green. Open: sase-core-revision.txt must move past the core commit once host finalizers land it (could not ratchet uncommitted core work); doctor bead-store SKIP test fails on pre-existing /home/bryan/sdd/beads, recorded as follow-up

## Dependencies

- **Depends on:** [sase-1bu.3](sase-1bu.3.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bu.7](sase-1bu.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.6/README.md) | [sase-1bu.6](sase-1bu.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`17d2beb`](https://github.com/sase-org/sase/commit/17d2beb7677cecb357680a93312b105f526620c2) | feat(goals): make goal a first-class builtin artifact kind (sase-1bu.6) | [sase-1bu.6](sase-1bu.6.md) | 2026-09-28 05:36:48 EDT |
| sase-core | [`sase-core@33b0250`](https://github.com/sase-org/sase-core/commit/33b0250f91b81ebe9913796574e5faf787f741cf) | feat(goals): make goal a first-class builtin artifact kind in sase-core (sase-1bu.6) | [sase-1bu.6](sase-1bu.6.md) | 2026-09-28 05:45:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bu.6][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.6/README.md

<!-- sase:referenced-by:end -->
