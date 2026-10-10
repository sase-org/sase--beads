# Bead: sase-1jm.2.1.5 — Bindings, facade, and shared corpus cache

[Bead Pages](../README.md) / [sase-1jm.2.1](sase-1jm.2.1.md) / sase-1jm.2.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.2.md) · **Assignee:** `sase-1jm.2.1.5` · **Size:** medium
**Created:** 2026-10-10 07:31:49 EDT · **Closed:** 2026-10-10 15:19:01 EDT
**Plan:** [202610/archive\_corpus.md](https://github.com/sase-org/sase--plans/blob/main/202610/archive_corpus.md)

## Description

bindings-cache: expose the corpus through PyO3 and one off-thread cache shared by the TUI and the CLI.

## Notes

[2026-10-10T19:18:39Z · sase-1jm.2.1.5] PROPOSED FOLLOW-UP: just check scoped lane is red on the clean base tree too — test_bob_dry_run_canonical_report_has_no_digest_suffix, test_contract_manifest_matches_marker_selection, test_tui_app_import_stays_under_startup_budget, test_tracked_marker_path_passing_sites_are_reviewed all fail identically with this phases files stashed (verified via git stash -u round-trip); needs an owner outside bindings-cache

[2026-10-10T19:18:45Z · sase-1jm.2.1.5] PROPOSED FOLLOW-UP: tests/ace/tui/test_node_finder_snapshot.py fails at collection on the clean base tree — imports test_query_hidden_on_both_flag_branches from test_node_finder_snapshot_hidden which does not define it; pre-existing, untouched by bindings-cache

[2026-10-10T19:19:01Z · sase-1jm.2.1.5] bindings-cache done and verified: 5 PyO3 bindings (compile/summarize/rows/lookup/count_agent_archive_corpus) in agent_custody, imported by module path and registered, with round-trip tests; AgentArchiveCorpus facade (compile plus 4 query ops, Python-side relative-date canonicalization) and one lazy process-wide cache keyed by (index signature, link-facet signature, agents-archive profile digest) with off-thread build and last-request-wins, serving TUI and CLI; 8 new Python tests pass; sase-core sase tool run check verdict pass; sase check: every lint gate passes and the scoped lane gave 54494 passed — its 6 failures plus 1 error reproduce identically on the clean base tree (2 more passed on retry as load flakes) and are recorded as PROPOSED FOLLOW-UP entries; epic-symbols clean; sase-core-revision.txt untouched for the host pin

## Dependencies

- **Depends on:** [sase-1jm.2.1.3](sase-1jm.2.1.3.md) ✓ · ⧖ 2026-10-10
- **Depends on:** [sase-1jm.2.1.4](sase-1jm.2.1.4.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.2.1.6](sase-1jm.2.1.6.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.2.1.5/README.md) | [sase-1jm.2.1.5](sase-1jm.2.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@bc40675`](https://github.com/sase-org/sase-core/commit/bc40675233d35f370e7bf915ddda170e695abf04) | feat(archive): bind corpus compile, summary, rows, lookup, and count | [sase-1jm.2.1.5](sase-1jm.2.1.5.md) | 2026-10-10 15:20:15 EDT |
