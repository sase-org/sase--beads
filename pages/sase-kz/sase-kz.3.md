# Bead: sase-kz.3 — PyO3 binding and wire parity for the session engine

[Bead Pages](../README.md) / [sase-kz](README.md) / sase-kz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zm.md) · **Assignee:** `sase-kz.3` · **Size:** small
**Created:** 2026-08-13 12:28:26 EDT · **Closed:** 2026-08-13 13:24:33 EDT
**Plan:** 202608/nested\_snippet\_sessions.md

## Description

core_binding: expose the session state machine to Python as a single wire-shaped binding, with binding-level tests and the lib.rs binding inventory updated.

## Notes

[2026-08-13T17:24:33Z · sase-kz.3] Added apply_snippet_session_event(state: dict, event: dict) -> dict in crates/sase_core_py/src/lib.rs (sase-core repo, uncommitted working tree), the session engine's single wire-shaped entry point, per the core_binding phase design. It dispatches on event['kind'] in {plan, expand, advance, retreat, apply_edit, clear} via a new pure sase_core::snippet_session::apply_session_event(state, SnippetSessionEvent) dispatcher (kept in the core crate, not the PyO3 layer). 'plan' is the stateless exception: it calls plan_snippet_expansion and echoes state back unchanged, since core_expansion/core_session never exposed the planner to Python and every later phase in this epic is Python-repo-only, so this was the only remaining chance to bind it. Result dict is rectangular: state, cursor_offset, text, tabstop_offsets always present, null/empty when not applicable. Registered in the lib.rs module inventory comment and the pymodule init. Added 12 new core-crate unit tests (including the reported-bug nesting scenario driven purely through events) and 2 PyO3 binding-level tests (nesting through dicts end-to-end, and malformed-state/unknown-event-kind rejection). Verified with ./scripts/check.sh all (fmt-check, clippy -D warnings, full cargo test --workspace): exit 0, no failures.

[2026-08-13T17:25:16Z · sase-kz.3] Implemented apply_session_event dispatcher in sase-core (snippet_session.rs) with tagged SnippetSessionEvent enum (plan/expand/advance/retreat/apply_edit/clear) and rectangular SnippetSessionEventResult; added PyO3 binding apply_snippet_session_event(state, event) -> dict in sase_core_py/lib.rs mirroring py_compose_snippet_catalog shape, registered in pymodule init + inventory comment. Folded stateless plan_snippet_expansion in as a 'plan' event on the same binding since later py-only phases (widget_engine) need it and cannot touch sase-core. 12 new core unit tests + 2 PyO3 binding tests (nested tabstop round trip via dict events, malformed-input rejection). Verified via 'just check' in sase-core (fmt-check + clippy -D warnings + full cargo test --workspace), exit 0.

## Dependencies

- **Depends on:** [sase-kz.2](sase-kz.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-kz.4](sase-kz.4.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kz.3/README.md) | [sase-kz.3](sase-kz.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0a8eeea`](https://github.com/sase-org/sase-core/commit/0a8eeea99d6f2360729fad4354383a5d6dc3b847) | feat(snippet-session): dispatch session events and bind to Python | [sase-kz.3](sase-kz.3.md) | 2026-08-13 13:25:59 EDT |
