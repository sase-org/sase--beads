# Bead: sase-1h8.8 — Read-model substrate, freshness protocol, and parity harness

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.8` · **Size:** medium
**Created:** 2026-10-06 18:59:39 EDT · **Closed:** 2026-10-07 09:19:09 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

read-model-store: add the versioned SQLite read model under the clone's git dir with an O(1) freshness token, full-rebuild fallback, transparent read integration, doctor --verify-cache, and a cache-vs-replay parity harness.

## Notes

[2026-10-07T02:50:52Z · sase-1h8.8] read-model-store landed: versioned SQLite read model under <git-dir>/sase/bead-read-model/<key>.sqlite (WAL) with O(1) freshness token (streams-dir mtime+inode + manifest/config sigs), full-sweep confirm, full-rebuild fallback with generation CAS, fail-open transparent integration in read_store_issues + show_issue_detail_with_options, doctor --verify-cache (-C) + cache status line, parity harness (replay-vs-cache + 30-step randomized mutation test + bench-corpus probes)

[2026-10-07T02:51:09Z · sase-1h8.8] Measurements (sase-core debug build, bench corpus 6899 beads/2000 streams/44735 events at 1x; 8x via prefix-copy: 55192 beads/16000 streams): 1x replay 1574ms (cold page cache) / cold rebuild 273ms / warm token-only reads ~250-279ms / cache 15.9MB; 8x replay 13786ms / cold rebuild 2508ms / warm ~2.2-2.3s / cache 127MB; verify-cache matched at both scales, generation stays 1 across warm reads. Warm serve still scales with total issues (full-snapshot deserialize) -- indexed point reads are read-model-queries (sase-1h8.12); the token path itself is 3 stats at any scale. Pre-existing rustfmt drift in 2 fingerprint files (clean-tree cargo fmt --check red) folded in so the gate passes.

[2026-10-07T04:30:56Z · sase-1h8.8--2] Snapshot drift from run c86ef5e5 (2 completion snapshot tests) repaired by regenerating tests/completion/snapshots/cli_spec.json via tools/sync_completion_spec; snapshot tests now pass locally, doctor suite 25 passed

[2026-10-07T04:49:47Z · sase-1h8.8--3] PROPOSED FOLLOW-UP: pre-existing symvision KNOWN private-import _runs in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py (witness 05b9fc696a324977dde864aadd60a092, established by sase-1h8.1) keeps just check red; out of scope for read-model phase

[2026-10-07T13:18:52Z · sase-1h8.8--1] PROPOSED FOLLOW-UP: just check exit 1 is 12 KNOWN only (triage verdict no_new_failures, ToolRun 7657c6103ed572e941084984c3c325df): 10 scoped-test KNOWNs in TUI/macro directive-completion, directive contract/parity, and TUI import-budget tests (witnesses 477276a723e911ef2ce08d5f4e412d7f, 0fe7e98b787b3772bdc79cef69fdbc64) plus 2 symvision KNOWNs already tracked in note #4 (witness 05b9fc696a324977dde864aadd60a092); none touch this phase files (bead_read_facade, cli_admin doctor, docs, core pin); out of scope for read-model phase

[2026-10-07T13:19:09Z · sase-1h8.8--1] Read-model phase verified: sase tool run check (ToolRun 7657c6103ed572e941084984c3c325df) triage verdict no_new_failures with zero new failures; read-model work (versioned SQLite read model, O(1) freshness token, full-rebuild fallback, doctor --verify-cache, parity harness, ratcheted core pin) intact; the 12 remaining failures are pre-existing KNOWNs in untouched TUI/macro areas recorded as PROPOSED FOLLOW-UP; epic-symbols clean

## Dependencies

- **Depends on:** [sase-1h8.1](sase-1h8.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.11](sase-1h8.11.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.4](sase-1h8.4.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.9](sase-1h8.9.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.8.md) | [sase-1h8.8](sase-1h8.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@91e0e49`](https://github.com/sase-org/sase-core/commit/91e0e49c083119e64118d7e56a6b51b1e0a13e84) | feat(bead): add versioned SQLite read model with freshness token and parity harness | [sase-1h8.8](sase-1h8.8.md) | 2026-10-07 00:57:36 EDT |
| sase | [`7da1570`](https://github.com/sase-org/sase/commit/7da15707ea0331e509f65553b5721f5e465c0d5a) | feat(bead-store): versioned SQLite read model with freshness token and verify-cache (sase-1h8.8) | [sase-1h8.8](sase-1h8.8.md) | 2026-10-07 09:20:33 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |
| read-by | [agent:sase-1h8.8--1][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1h8.8--3][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1h8.9--1][3] | check pre-existing KNOWNs for sase-1h8.9 close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.8.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.9.md

<!-- sase:referenced-by:end -->
