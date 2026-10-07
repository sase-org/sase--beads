# Bead: sase-1h8.9 — Snapshot-plus-tail incremental refresh

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.9` · **Size:** medium
**Created:** 2026-10-06 18:59:40 EDT · **Closed:** 2026-10-07 12:19:03 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

read-model-tail: apply appended events after the merge frontier instead of rebuilding, falling back to a rebuild on any precondition failure, with randomized parity and outcome telemetry.

## Notes

[2026-10-07T15:50:09Z · sase-1h8.9] read-model-tail landed (sase-core, uncommitted in linked checkout): snapshot-plus-tail incremental refresh in crates/sase_core/src/bead/read_model/tail.rs. On a sweep with changes the cache verifies 4 preconditions (pure append via stored length + SHA-256 prefix hash with line-boundary rule; no stream removed/renamed; manifest version+count consistent with pure additions; parsed config equal modulo default-materialization and next_counter cursor; every new merge key strictly after stored frontier) then parses only appended bytes, merges the tail in full stream order, and resumes onto touched rows (compact id/ref/created_at/parent index + touched-row loads; collapse winners recomputed over the index; positions renumbered only on id-set change; edges rescoped; provenance as in-order SQL transitions). Any precondition failure rebuilds from full replay with the reason in telemetry. Fast path skips the index entirely when the tail has no creations/removals/ref-mentions. Fixed two O(history) traps found by measurement: quadratic removed-stream scan, and manifest provenance-string comparison.

[2026-10-07T15:50:35Z · sase-1h8.9] Measurements (debug build, bench corpus 6899 beads/2000 streams/44735 events at 1x; 8x prefix-copy 55192 beads/16000 streams): 1x replay 1569-2007ms / cold rebuild 266-318ms / warm token serve ~250ms / tail-read 310-368ms with tail path taken (refresh work ~60ms); 8x replay ~13-14.5s / cold rebuild ~2.3s / warm ~2.2s / tail-read ~2.4s (refresh work ~200-250ms vs rebuild work ~2.3s, ~9-11x). End-to-end reads stay serve-load-dominated (full-snapshot deserialize, known from sase-1h8.8); indexed point reads are sase-1h8.12 territory. Serve/tail/rebuild outcome counters + last refresh/reason recorded in cache meta, surfaced in doctor status wire v2 and the doctor line. doctor --verify-cache matched at every step of every harness run. Cache footprint unchanged (16MB at 1x, 127MB at 8x).

[2026-10-07T15:50:53Z · sase-1h8.9] Verification: 17 read-model unit tests (tail note/create/removal/closed-bead-write + fallback backdate/rewrite/config + serve counting), extended bead_read_model_parity (30-step randomized with per-step verify+exactly-one-refresh accounting; adversarial skew-ahead/behind, links, deps, +1/snooze/wake, close/note-edit/retract/reopen, relocation-shaped mid-stream insert, conflict-shaped reserialization, whole-issue removal, creation; 4-reader concurrent interleave asserting every snapshot equals a replay state) all green; bead event/read/storage parity + mutation(148) + events(42) + jsonl(19) + py binding (wire v2) + pytest test_cli_doctor (24) green; clippy clean; prettier fixed for docs edits. Telemetry render in src/sase/bead/cli_admin.py with legacy-dict tolerance; docs/beads.md + docs/rust_backend.md tail paragraphs.

[2026-10-07T15:51:10Z · sase-1h8.9] PROPOSED FOLLOW-UP: sase-core check has 1 failure in editor::directive::tests::contract_covers_the_audited_directive_matrix (expects 6 directives, code yields 7 with for_epic) in uncommitted editor files I never touched (shared linked checkout, likely a cohabiting agent); all bead suites pass. Needs triage by the directive owner.

[2026-10-07T15:51:20Z · sase-1h8.9] PROPOSED FOLLOW-UP: sase-core tail changes are uncommitted in the linked checkout so sase-core-revision.txt still pins 91e0e49c; ratchet the pin past the sase-core tail commit once it lands remotely, then confirm doctor telemetry against the new core.

[2026-10-07T16:19:03Z · sase-1h8.9--1] verified: 17 read-model tail unit + parity incl adversarial+concurrency + 24 doctor tests green; bench 1x tail-read ~310ms with ~60ms refresh, 8x ~2.4s with ~200ms refresh vs ~2.3s rebuild; sase check fmt/lints/SASE-validation green; sase tool run check 2a2ccc3e triage verdict no_new_failures (4 KNOWN only: 2 symvision _runs witness 05b9fc69, TUI import-budget witness 0fe7e98b, finalizers-discard-guard witness be557ed1; none in bead/cli_admin/docs phase files); epic-symbols clean

## Dependencies

- **Blocks:** [sase-1h8.10](sase-1h8.10.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.12](sase-1h8.12.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.8](sase-1h8.8.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.9.md) | [sase-1h8.9](sase-1h8.9.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f8d05ef`](https://github.com/sase-org/sase-core/commit/f8d05efc58310eca985f2112afc89379ff7a6636) | feat(bead-read-model): snapshot-plus-tail incremental refresh in sase-core | [sase-1h8.9](sase-1h8.9.md) | 2026-10-07 12:20:26 EDT |
| sase | [`aebe28d`](https://github.com/sase-org/sase/commit/aebe28de8414ebc34438e4fb4d57fc7519153b08) | feat(bead-read-model): snapshot-plus-tail incremental refresh telemetry and doctor tests | [sase-1h8.9](sase-1h8.9.md) | 2026-10-07 13:09:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |
| read-by | [agent:sase-1h8.9--1][2] | Need phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.9.md

<!-- sase:referenced-by:end -->
