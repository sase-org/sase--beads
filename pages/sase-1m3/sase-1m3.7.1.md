# Bead: sase-1m3.7.1 — Committed code snapshots and records for project statistics

[Bead Pages](../README.md) / [sase-1m3.7](sase-1m3.7.md) / sase-1m3.7.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) · **Assignee:** `sase-1m3.7.1.land`
**Created:** 2026-10-17 02:56:50 EDT
**Plan:** [202610/project\_stats\_code\_records.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/project_stats_code_records.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:cf44a5d9c96251754e7b7e5f | attached via sase artifact create --bead |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md

<!-- sase:links:end -->

## Description

Complete sase-1m3.7 with accurate cached code snapshots, an evidenced line-counter choice, and metadata-only records summaries exposed by project_stats_query.

## Notes

[2026-10-18T03:15:58Z · sase-1lh.7.5.4.3.3.4.4.land] DISCOVERED ISSUE: Landing audit of sase-1lh.7.5.4.3.3.4.4, prompted by watch phase sase-1lh.7.5.4.3.3.4.4.3 note #1, independently verified core PR #331 macOS job 117563429625 in run 39089637894 fails project_stats::snapshot::tests::odd_filenames_and_non_utf8_paths_are_preserved at snapshot/tests.rs:222: fs::write of src/\xff.rs returns OS 92 Illegal byte sequence. 5171 passed, 1 failed, 4 ignored; mobile_pairing permissions/umask/symlink tests pass on macOS. Actual source and git history identify introducing commit 733256ede964bc99e46f8ce7faffb690df0c6a49, owned by your phase sase-1m3.7.1.2. It predates the release-portability epic; not caused by its openat fix. This deterministic filesystem-dependent fixture blocks core 0.42.0 and the sase 0.18.0 release. Preserve non-UTF8 Git-tree coverage while making fixture construction independent of filesystem filename restrictions (for example, construct the Git index/tree using raw-byte NUL-delimited records rather than writing that path to disk). Do not skip or weaken the required assertion. Full CI log: file:explicit:cf44a5d9c96251754e7b7e5f; https://github.com/sase-org/sase-core/actions/runs/39089637894/job/117563429625. sase_new_task all-status searches, last-week task sweep, and active-epic review found no duplicate task; routed here as the causal active epic instead of creating a task or another release repair epic.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.land/README.md) | [sase-1m3.7.1](sase-1m3.7.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.7.1.1][1] | Need the child epic decisions and phase-wide implementation constraints | 1 |
| read-by | [agent:sase-1m3.7.1.3][2] | Need the governing epic decisions for the assigned phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.7.1.3/README.md

<!-- sase:referenced-by:end -->
