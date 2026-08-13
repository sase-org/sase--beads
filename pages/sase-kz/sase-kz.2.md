# Bead: sase-kz.2 — Rust nested snippet session state machine

[Bead Pages](../README.md) / [sase-kz](README.md) / sase-kz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zm.md) · **Assignee:** `sase-kz.2` · **Size:** medium
**Created:** 2026-08-13 12:28:09 EDT · **Closed:** 2026-08-13 13:10:25 EDT
**Plan:** 202608/nested\_snippet\_sessions.md

## Description

core_session: add the pure session state machine over a flat ordered stop list — nest-vs-reset on expand, advance/retreat, and absolute-anchor remapping from document edit deltas.

## Notes

[2026-08-13T17:10:25Z · sase-kz.2] Implemented expand/advance/retreat/apply_edit/clear over the flat ordered stop list in crates/sase_core/src/snippet_session.rs per the core_session phase design (nest-vs-reset containment rule, depth cap 8, sticky-right stop remap, sticky-left/right session span remap, versioned schema_version=1 wire repr). Added session_tests covering the reported nesting bug, reset on non-contained expand, no-stop-plan nesting/reset, two levels of nesting, depth-cap overflow, retreat/advance boundary no-target cases, edit remapping before/at/inside/after stops, deleting a whole nested expansion, unordered edit bounds, and JSON field-order round-trip. Found and fixed a hand-computed arithmetic error in the reported-bug test's expected offsets (test expected [4,8,12,15]/8/12/15 for 'foo $1 bar $2 baz $3 buz', but the ported Python semantics correctly leave double spaces where each $N marker is removed, yielding [4,9,14,18]/9/14/18 — verified by hand against _snippets.py's identical algorithm). Verified with ./scripts/check.sh all (fmt-check, clippy -D warnings, full cargo test --workspace including sase_core_py binding tests): exit 0, no failures.

## Dependencies

- **Depends on:** [sase-kz.1](sase-kz.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-kz.3](sase-kz.3.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kz.2/README.md) | [sase-kz.2](sase-kz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ca59ed9`](https://github.com/sase-org/sase-core/commit/ca59ed9b42159feeeaa12fe015d094c64179fedf) | feat(snippet-session): add nested snippet session state machine | [sase-kz.2](sase-kz.2.md) | 2026-08-13 13:11:51 EDT |
