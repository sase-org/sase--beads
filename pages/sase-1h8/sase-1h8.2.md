# Bead: sase-1h8.2 — Constant-cost artifact-link outbox append

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.2` · **Size:** small
**Created:** 2026-10-06 18:59:30 EDT · **Closed:** 2026-10-06 19:27:22 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

outbox: stop re-reading and re-canonicalizing every outbox entry on each append (~2.9 s of every audited read) while keeping operation-id collision semantics.

## Notes

[2026-10-06T23:07:36Z · sase-1h8.2] Outbox composition (gh_sase-org__sase, 11,446 lines / 7.8 MB): edge-put 6,985 all from sase.artifact-link-derived (trusted machine events, always eligible); observation 4,275 from 998 distinct agents (need per-run release evidence); alias 186 from sase.artifact-link-renames (trusted). No artifact-link-outbox-dropped.jsonl exists, so stale-terminal drops have never fired.

[2026-10-06T23:07:51Z · sase-1h8.2] Measured append cost on a copy of the live 11,449-line outbox: old code 1.762s with 11,449 Rust classify calls (plus json.loads + canonicalize per event line); new code 0.007-0.015s with 0 classify calls. uuid4-minted appends skip the scan entirely; caller-supplied ids scan only lines containing the exact quoted id token. Collision semantics unchanged (different-bytes reuse raises; identical re-append accepted).

[2026-10-06T23:08:02Z · sase-1h8.2] PROPOSED FOLLOW-UP: ~7k eligible trusted-machine entries (derived edge-put + alias) remain queued even though drain paths run (commit workflow, derivation self-drain, backfill chop); the backlog looks publish-side (machine-writability/push), not a never-running drain path, so it needs a publish-side investigation, not a scheduling fix.

[2026-10-06T23:27:04Z · sase-1h8.2--1] PROPOSED FOLLOW-UP: symvision private-import errors for _runs in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py fail just check on clean base (both present at HEAD, untouched by this phase; triage KNOWN witness 05b9fc696a324977dde864aadd60a092, no owner)

[2026-10-06T23:27:22Z · sase-1h8.2--1] Outbox append is constant-cost: uuid4-minted ids skip collision scan (0 classify calls, 0.007-0.015s vs 1.762s on 11.4k-line outbox); caller-supplied ids scan only lines with exact quoted id token; collision semantics unchanged. Verified: tests/main/test_artifact_link_outbox_io.py 7 passed; just check scoped tests passed; 2 symvision _runs failures are pre-existing on clean base (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1h8.14](sase-1h8.14.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.2.md) | [sase-1h8.2](sase-1h8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`545caa7`](https://github.com/sase-org/sase/commit/545caa7abdfb746e83900b2fc1590f40635783d2) | feat(outbox): constant-cost artifact-link outbox append (sase-1h8.2) | [sase-1h8.2](sase-1h8.2.md) | 2026-10-06 19:28:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.3y.grk][1] | Need 1h8 phase statuses that overlap sase-1h5 Beads-pane work | 1 |
| read-by | [agent:sase-1h8.2--1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3y.grk/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.2.md

<!-- sase:referenced-by:end -->
