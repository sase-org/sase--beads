# Bead: sase-1kj.5 — Stop the Patch relation-index treadmill

[Bead Pages](../README.md) / [sase-1kj](README.md) / sase-1kj.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.102](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.102.md) · **Assignee:** `sase-1kj.5` · **Size:** medium
**Created:** 2026-10-13 11:47:19 EDT · **Closed:** 2026-10-13 13:43:24 EDT
**Plan:** [202610/apollo\_tui\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202610/apollo_tui_startup.md)

## Description

patch-relation-index: memoize the Patch relation index, build its edges only when the Patches pane is visible (keeping a cheap targets-only index for link-follow), take the startup build off the event loop, and debounce visible reloads adaptively.

## Notes

[2026-10-13T17:42:54Z · sase-1kj.5] PROPOSED FOLLOW-UP: Reduce the pre-existing TUI app import closure below its 3513-module cap — clean-base merge-base 1a638eac95b42c13014dd76c384dbfb56f5b323f and this tree both load 3518 modules, with 0 module delta from this phase; check triage attached no task owner.

[2026-10-13T17:43:24Z · sase-1kj.5] Implemented deferred, memoized Patch relation indexing and off-loop startup preparation. just fmt and 7 focused tests passed; scoped check passed lint/SASE validation and 55,503 tests but failed on one KNOWN AcePageGroup witness and the TUI import-budget baseline (3,518 modules vs 3,513). Verified the same 3,518-module closure at clean base commit 1a638eac95b42c13014dd76c384dbfb56f5b323f with zero module delta; recorded that baseline as PROPOSED FOLLOW-UP. epic-symbols reported none.

[2026-10-13T18:09:06Z · sase-1kj.5] Recovery turn: previous close had no landed commit. Implemented deferred/memoized Patch relation indexing, visibility-gated edges, off-loop startup prepare, and adaptive refresh debounce. 111 focused tests passed (new test_patch_relation_index plus wiring/reload/y-keymap/dirty-flags/nav-gate/reveal/ace-testing). Hidden 10x source_key churn: 0 real builds. Visible same-key memo: 1 real build.

## Dependencies

- **Blocks:** [sase-1kj.6](sase-1kj.6.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.7](sase-1kj.7.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1kj.8](sase-1kj.8.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kj.5.md) | [sase-1kj.5](sase-1kj.5.md) | 0 |
