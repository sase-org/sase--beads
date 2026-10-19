# Bead: sase-1m3.7.1 — Committed code snapshots and records for project statistics

[Bead Pages](../README.md) / [sase-1m3.7](sase-1m3.7.md) / sase-1m3.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) · **Assignee:** `sase-1m3.7.1.land`
**Created:** 2026-10-17 02:56:50 EDT · **Closed:** 2026-10-18 21:24:47 EDT
**Plan:** [202610/project\_stats\_code\_records.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/project_stats_code_records.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:cf44a5d9c96251754e7b7e5f | attached via sase artifact create --bead |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md

<!-- sase:links:end -->

## Description

Complete sase-1m3.7 with accurate cached code snapshots, an evidenced line-counter choice, and metadata-only records summaries exposed by project_stats_query.

## Notes

[2026-10-18T03:15:58Z · sase-1lh.7.5.4.3.3.4.4.land] DISCOVERED ISSUE: Landing audit of sase-1lh.7.5.4.3.3.4.4, prompted by watch phase sase-1lh.7.5.4.3.3.4.4.3 note #1, independently verified core PR #331 macOS job 117563429625 in run 39089637894 fails project_stats::snapshot::tests::odd_filenames_and_non_utf8_paths_are_preserved at snapshot/tests.rs:222: fs::write of src/\xff.rs returns OS 92 Illegal byte sequence. 5171 passed, 1 failed, 4 ignored; mobile_pairing permissions/umask/symlink tests pass on macOS. Actual source and git history identify introducing commit 733256ede964bc99e46f8ce7faffb690df0c6a49, owned by your phase sase-1m3.7.1.2. It predates the release-portability epic; not caused by its openat fix. This deterministic filesystem-dependent fixture blocks core 0.42.0 and the sase 0.18.0 release. Preserve non-UTF8 Git-tree coverage while making fixture construction independent of filesystem filename restrictions (for example, construct the Git index/tree using raw-byte NUL-delimited records rather than writing that path to disk). Do not skip or weaken the required assertion. Full CI log: file:explicit:cf44a5d9c96251754e7b7e5f; https://github.com/sase-org/sase-core/actions/runs/39089637894/job/117563429625. sase_new_task all-status searches, last-week task sweep, and active-epic review found no duplicate task; routed here as the causal active epic instead of creating a task or another release repair epic.

[2026-10-18T14:15:55Z · sase-1mk.1] core-fixture (sase-1mk.1) resolves this epic's DISCOVERED ISSUE: odd_filenames_and_non_utf8_paths_are_preserved no longer writes src/\xff.rs to disk; it stages the blob via git hash-object + update-index --cacheinfo (new test_support::stage_blob_at_raw_path), so macOS CI no longer hits EILSEQ. Pending host commit to sase-core master.

[2026-10-18T22:51:13Z · sase-1m3.7.1.land] LAND TRIAGE of PROPOSED FOLLOW-UPs (all from sase-1m3.7.1.5): #5 stale sase_artifact skill -> created memory task sase-1ms (small; orphaned 2026-07-03 deployment never added to the retired-skill pruning list, not caused by this epic). #6 Code cold/changed-tip runtime budget miss -> not a new task: noted as a DISCOVERED ISSUE on outer epic sase-1m3, whose budgets phase sase-1m3.12 owns it, as the approved plan routes unresolved budget misses to the outer land agent. The landing tale still fixes two epic-caused cost contributors (cache growth, double evidence scan). #7 gateway IPC flake -> +1 on existing sase-1gz (now +6). #12 primary TUI failures -> +1 on sase-1l3 (test_session_collapsed_detached_macro_skips_markers), sase-1ia (member_loader prompt precedence) and sase-1ki (bottom pin), all reproduced on the clean baseline; test_startup_update_toast_appears_once_in_tui (failed in the full lane, passed 2 focused retries) -> created flake task sase-1mr. Epic note #1 macOS non-UTF8 fixture: verified resolved by core 80dc704a (stage_blob_at_raw_path) on origin/master before v0.42.0. sase-1m3.7 note #1 (skipped decision record) is the outer epic's, so it is not duplicated here.

[2026-10-18T22:53:50Z · sase-1m3.7.1.land] LAND VERIFICATION: all 5 phases closed and landed in sase-core (df833a04, 9c16796d, 733256ed, 99b10bd0, b8737fa5, plus macOS fix 80dc704a); sase pin is b8737fa5; no epic-symbols. Source review confirmed the wire, records, query, and tokei contracts. It also found epic-caused remaining work, now planned as a landing tale: (1) classifier false positives: 75 src/sase/memory/*.py and 6 src/sase/skills/*.py counted as agent_context, sase-core's own project_stats/snapshot/*.rs excluded as generated (bare snapshot/gen/target dirs), and .txt always treated as prose; (2) the attribute temp repo inherits global init config and templates, which breaks SHA-256 repos and leaks template info/attributes; (3) the per-blob cache never prunes stale OIDs; (4) the clone-disagreement issue is computed over failed clones and overwrites the chosen clone's own issue; (5) records tests the plan required (merges, corrupt cache, new-tip refresh) are missing, and log.showSignature is not pinned; (6) six stale #![allow(dead_code)], snapshot/mod.rs is not a facade, and blob evidence is scanned twice. Integration: the sibling parent-epic phases (core plans/directory 7a46109f/3b3b7401; sase loader 2cae86a1aa, registry c68a30365f) already consume or are integrated with the new wire; only the Python counter default ('nonblank') needs aligning to 'sloc'.

[2026-10-19T01:24:47Z · sase-1m3.7.1.land--2] LAND VERIFICATION: all five phases landed in sase-core commits df833a04, 9c16796d, 733256ed, 99b10bd0, b8737fa5; macOS fixture fix 80dc704a is on master. Tokei 15.0.0 passed: +0.152072 MiB wheel, 1.107937x clean build time. Plan status is done.

Counts are from the rebuilt binding on committed trees; before values reconstruct the old classifier on the same trees.
1. Classifier: SASE 12,435→12,516 code files; 75 memory and 6 skills Python files moved agent_context→source. Core 1,152→1,158; all 6 tracked project_stats/snapshot Rust files moved generated→source. requirements-docs.txt moved docs→config_data.
2. Attribute-session isolation: SASE 12,516→12,516; core 1,158→1,158.
3. Stale blob-cache pruning: SASE 12,516→12,516; core 1,158→1,158.
4. Clone-disagreement issue fix: SASE 12,516→12,516; core 1,158→1,158.
5. Records/cache regressions and log.showSignature pin: SASE 12,516→12,516; core 1,158→1,158.
6. Removed six dead_code allows, split snapshot/measure.rs, reused blob evidence: SASE 12,516→12,516; core committed HEAD query 1,158, with the new measure.rs adding one source file in the pending landing (1,159).

Passing test ToolRuns: 63a9f3323beb2da7c423ac7524dbcaec (core), 079969d16abef454e3015f045a5329f9 (binding), ada596b0a27e817b4324bae1af1bb50a (snapshot). Passing core checks: 2e5b8d16053c273127bab9051d4222fa, 1b69537c51496b32559ca24cfe13dca1, bf961099c9a0f8e3e73209be665ef1b8. SASE fmt/symvision passed; both epic-symbol lists are empty. SASE check 2ebf33c45edf385d28ffd2cab8a6d4b1 exited 1 (56,451 passed, 34 skipped, 31 failed; triage 12 NEW, 16 KNOWN, 1 FLAKY). Failures are in TUI, marker-audit, update-progress, CLI, and selector tests; the only SASE diff is the stats counter default in models.py, outside those paths. This check is recorded as failed.

Existing follow-up triage remains: memory task sase-1ms, flake task sase-1mr, +1s on sase-1gz/1l3/1ia/1ki, and the runtime issue on outer epic sase-1m3. No triage was repeated.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.1.land.md) | [sase-1m3.7.1](sase-1m3.7.1.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6a626d1`](https://github.com/sase-org/sase-core/commit/6a626d10091dd3888973d77dd2b55a92d8cd41f9) | fix(project-stats): complete classifier and snapshot landing | [sase-1m3.7.1](sase-1m3.7.1.md) | 2026-10-18 21:27:23 EDT |
| sase | [`dd963c0`](https://github.com/sase-org/sase/commit/dd963c0fa64ab25beeaf84ac8e9d073bbb518c91) | fix(stats): align project code counter with SLOC | [sase-1m3.7.1](sase-1m3.7.1.md) | 2026-10-18 21:32:50 EDT |
| sase--plans | [`sase--plans@b0dac8f`](https://github.com/sase-org/sase--plans/commit/b0dac8fe62572f4f659225ee43bc083c8ea51d2c) | docs(plan): mark project stats plan done | [sase-1m3.7.1](sase-1m3.7.1.md) | 2026-10-18 21:36:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.7.1.1][1] | Need the child epic decisions and phase-wide implementation constraints | 1 |
| read-by | [agent:sase-1m3.7.1.3][2] | Need the governing epic decisions for the assigned phase | 1 |
| read-by | [agent:sase-1m3.7.1.4][3] | Need parent epic DECISIONS and phase notes | 1 |
| read-by | [agent:sase-1m3.7.1.land--2][4] | Verify child epic close note and status after approved landing closeout | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.4/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.1.land.md

<!-- sase:referenced-by:end -->
