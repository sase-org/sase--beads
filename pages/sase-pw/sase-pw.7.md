# Bead: sase-pw.7 — Agents-tab project scoping

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.7` · **Size:** medium
**Created:** 2026-08-18 11:30:35 EDT · **Closed:** 2026-08-18 15:58:38 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

agents: seed the Agents-tab search query with the current project behind the default-off `seed_agents_query` setting, and attribute a seeded scope visibly in the info panel.

## Notes

[2026-08-18T19:14:52Z · sase-pw.7] PROPOSED FOLLOW-UP: tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind is broken on HEAD — demo_flag() no longer accepts default= after c5a0dcf4a (flag default now comes from kind). Unrelated to Agents-tab seeding; just check hits it only when the suite escalates (Justfile is in the broadening set because this phase consumed resolve_current_project / CurrentProject and dropped those stale --epic-symbol entries).

[2026-08-18T19:15:10Z · sase-pw.7] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py (test_checked_in_snapshot_has_no_drift, test_current_structural_view_matches_checked_in_snapshot) fail with dict key-order drift against the argparse tree; no CLI in this phase. Same full-suite escalation as the flag integrity test.

[2026-08-18T19:58:11Z · sase-pw.7--2] PROPOSED FOLLOW-UP: project_accent, project_accent_map, and peek_current_project_change_token still have no non-test callers in this tree. After sase-pw.8 closed at 2026-08-18T19:51:14Z, they were re-keyed onto parent sase-pw so Justfile --epic-symbol entries would not go stale. Land should consume them or drop the whitelist once a real caller lands.

[2026-08-18T19:58:38Z · sase-pw.7--2] Verified seed_agents_query false leaves the Agents-tab query empty (no resolve, no seed). When true, the agent-load worker resolves the current project and seeds _agent_search_query via project_query_term(display_name) as project:<display_name> before apply/finalize. Info panel shows a dim seeded tag and _edit_agent_search_query clears it. Unread-jump candidates and prospective clans honor the same _agent_search_query: finalize filters the list, _apply_active_agent_query filters clan reveal targets, and the unread cache key includes the query. project: matcher also honors project_display_name. sase bead epic-symbols sase-pw.7: no leftovers. just check lint was green after the first leftover re-key. Scoped just check ran 33502 tests / 13 skipped and failed only the known pre-existing HEAD trio (tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind; tests/completion/test_snapshot.py::test_current_structural_view_matches_checked_in_snapshot plus the matching checked-in drift gate) — out of scope, already recorded as PROPOSED FOLLOW-UP. Leftover sase-pw.4 epic-symbols were re-keyed (peek_current_project_change_token to parent sase-pw; project_accent and project_accent_map first to still-open sase-pw.8). After sase-pw.8 closed at 2026-08-18T19:51:14Z, project_accent and project_accent_map were re-keyed again onto parent sase-pw; just _lint-symvision is green. Targeted seed/unread-jump/query/info-panel tests: 84 passed.

[2026-08-18T20:00:22Z · sase-pw.7--2] seed_agents_query false leaves the query empty; true seeds project:<display_name> from the load worker; info panel shows a dim seeded tag and _edit_agent_search_query clears it; unread-jump candidates and prospective clans honor the same _agent_search_query (finalize filters the list; _apply_active_agent_query filters clan reveal targets; the unread cache key includes the query); just check lint was green; scoped suite 33502 passed / 13 skipped / 3 failed — the known pre-existing HEAD trio (feature_flags test_kind_mismatch_when_default_disagrees_with_kind plus two completion snapshot key-order tests), not this phase; leftover sase-pw.4 epic-symbols were re-keyed (peek_current_project_change_token to parent sase-pw; project_accent and project_accent_map first to sase-pw.8, then to parent sase-pw after sase-pw.8 closed).

## Dependencies

- **Depends on:** [sase-pw.1](sase-pw.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.3](sase-pw.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.9](sase-pw.9.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.7.md) | [sase-pw.7](sase-pw.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`831fa6b`](https://github.com/sase-org/sase/commit/831fa6bcbf5bfad84ae88b41c8eddd885ad48490) | feat(ace): seed Agents-tab query from the current project | [sase-pw.7](sase-pw.7.md) | 2026-08-18 16:02:26 EDT |
