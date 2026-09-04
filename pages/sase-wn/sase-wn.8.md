# Bead: sase-wn.8 — Small ace I/O fixes (agents-sync reads, bead N+1)

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.8` · **Size:** small
**Created:** 2026-09-04 12:11:14 EDT · **Closed:** 2026-09-04 15:38:00 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-io-hygiene: replace the byte-at-a-time _read_until_nul in agents_sync git blob reads with buffered reads, and batch the per-bead show() N+1 in the prompt-panel detail header summary.

## Notes

[2026-09-04T19:34:07Z · sase-wn.8] ace-io-hygiene: buffered git cat-file --batch -Z reads via leftover buffer + read1 (headers) and exact length-prefixed body reads; bead_statuses_for_project now one list_issues query (Rust bead_show is single-id only). Privatized in-file-only _compute_fs_trigger_token to clear a pre-existing unused-public-symbol lint.

[2026-09-04T19:35:12Z · sase-wn.8] PROPOSED FOLLOW-UP: split link_follow.py under toobig — src/sase/ace/tui/actions/link_follow.py is 1066 lines (limit 1000) on master; just check fails independently of this phase.

[2026-09-04T19:36:09Z · sase-wn.8] PROPOSED FOLLOW-UP: Rust bead multi-get — wait-bead statuses still hydrate every issue through list_issues because bead_show has no multi-get binding; a store-side statuses-for-ids would be cheaper on large stores.

[2026-09-04T19:38:00Z · sase-wn.8] Buffered git cat-file --batch -Z reads (leftover after header NUL, chunked bodies, oversized/non-blob drain) plus one-session incoming-cache test; bead_statuses_for_project uses one list_issues (no per-id show), including unique suffix match and empty-id short-circuit. sase bead epic-symbols sase-wn.8: none. just check: fmt/ruff/mypy/symvision green; toobig still fails on pre-existing link_follow.py 1066 lines (recorded as PROPOSED FOLLOW-UP).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.8/README.md) | [sase-wn.8](sase-wn.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c0ae9d2`](https://github.com/sase-org/sase/commit/c0ae9d2d05901cfd9a96f36fdf8240ae2804f1bd) | perf(ace): buffer cat-file reads and batch wait-bead status lookups | [sase-wn.8](sase-wn.8.md) | 2026-09-04 15:40:57 EDT |
