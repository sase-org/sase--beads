# Bead: sase-1g4.2.1.4 — Python catalogs, mobile and highlight wires, and macro show

[Bead Pages](../README.md) / [sase-1g4.2.1](sase-1g4.2.1.md) / sase-1g4.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.md) · **Assignee:** `sase-1g4.2.1.4` · **Size:** medium
**Created:** 2026-10-05 02:19:28 EDT · **Closed:** 2026-10-05 03:39:09 EDT
**Plan:** [202610/macro\_choice\_wires\_lsp.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_choice_wires_lsp.md)

## Description

projections: preserve rich input metadata in Python catalog, mobile, and highlight projections, use Rust type labels in signatures and macro show, mirror the golden corpus, and test candidate edits against the binder.

## Notes

[2026-10-05T07:38:43Z · sase-1g4.2.1.4] PROPOSED FOLLOW-UP: Refresh the pinned-core setup probes — sase tool run check 9cc5ce6eb9a6e8468e6d24c89515714e failed during setup because the unchanged sase_content_layout binding reports schema 6 while the probe expects 5; the same clean pinned-core mismatch is recorded in sase-1g4.1 note #1 (including the stale stats probe). No standalone task bead surfaced in search. The rebuilt pinned extension ran this phase’s focused Python suite successfully (108 passed).

[2026-10-05T07:39:09Z · sase-1g4.2.1.4] Verified Python catalog/mobile/highlight/show metadata projections, pinned-core candidate and parser/binder parity, and byte-identical golden corpus; focused suite passed 108 tests. sase tool run check is blocked in setup by the known clean-core sase_content_layout schema 6 vs probe schema 5 mismatch, recorded as a proposed follow-up. epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-1g4.2.1.1](sase-1g4.2.1.1.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1g4.2.1.5](sase-1g4.2.1.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.4/README.md) | [sase-1g4.2.1.4](sase-1g4.2.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`399b13f`](https://github.com/sase-org/sase/commit/399b13f3efa427ddc549ff82c0135a505053f894) | feat(macro): preserve input choice metadata | [sase-1g4.2.1.4](sase-1g4.2.1.4.md) | 2026-10-05 03:40:35 EDT |
