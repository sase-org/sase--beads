# Bead: sase-fr.1 — Durable close history in the bead event reducer

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.1` · **Size:** medium
**Created:** 2026-08-05 21:18:21 EDT · **Closed:** 2026-08-05 21:47:23 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

core-model: add BeadCloseRecordWire and IssueWire.close_history to sase-core, archive close metadata instead of discarding it on every reopen path, unify the mutation and reducer paths on one helper, and release.

## Notes

[2026-08-06T01:48:30Z · sase-fr.1] Landed as sase-core PR #86 (https://github.com/sase-org/sase-core/pull/86), branch sase-core_bead-close-history-core-model_1, commit 66011f5. NOT YET MERGED, so no release version exists yet. sase-fr.2 (core-adopt) MUST read the release version off master after #86 merges rather than assuming one. Because this is an additive `feat`, release-plz will cut a MINOR bump: current master is v0.18.1 with release PR #85 (v0.18.2) already pending, so the version to adopt will be 0.19.0 and the sase-core-rs window becomes >=0.19.0,<0.20.0. Per the plan Sequencing section that ceiling supersedes both of the CI-recovery epic bumps; confirm the commit-budget fix is included in 0.19.0 before raising it.

[2026-08-06T01:48:47Z · sase-fr.1] Verified: cargo test -p sase_core all green (1224 lib + 15 integration suites, 0 failed); cargo clippy -p sase_core --all-targets clean; cargo fmt applied. New coverage: mutation-vs-reducer parity for all four reopen causes (plus_one, open incl. reopened ancestors, update, epic_preclaim), retroactive recovery from the event log with a close_history-stripped issues.jsonl, the (reporter, timestamp) join invariant, multi-episode oldest-first ordering with correct causes, the never-closed no-op guard, and wire round-trip + blank-field validation + empty-history byte-identical serialization. Confirmed the parity test is load-bearing: temporarily restoring the old open_issue body (resolution = None only) makes it fail with projected closed_at=Some(...) vs reduced close_history=[...].

[2026-08-06T01:49:03Z · sase-fr.1] PROPOSED FOLLOW-UP: Rust search_issues cannot find archived close reasons — crates/sase_core/src/bead/search.rs indexes plus_one_evidence but has no close_history field, so once the cli phase adds close_history_search_text to the Python index the two search paths will disagree; add it to BEAD_SEARCH_FIELD_NAMES and the Rust haystack.

[2026-08-06T01:49:12Z · sase-fr.1] PROPOSED FOLLOW-UP: sase bead history does not surface close_history changes — crates/sase_core/src/bead/history.rs enumerates tracked fields explicitly and was not extended, so a reopen shows no history entry for the archived record.

[2026-08-06T01:49:38Z · sase-fr.1] core-model implemented in sase-core and landed as PR #86; cargo test/clippy/fmt all green locally, mutation-vs-reducer parity proven load-bearing against the pre-change open_issue.

[2026-08-06T01:52:11Z · sase-fr.1] CI on sase-core PR #86 is fully green: cargo fmt + clippy + test (1m59s) pass, maturin build + import smoke (3m59s) pass, Cargo version guard pass, Conventional PR title pass. PR is awaiting review/merge.

## Dependencies

- **Blocks:** [sase-fr.2](sase-fr.2.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.1/README.md) | [sase-fr.1](sase-fr.1.md) | 0 |
