# Bead: sase-1ko.9 — Grok full-bundle rules and Muse prompt-prefix delivery

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.9` · **Size:** medium
**Created:** 2026-10-13 18:10:37 EDT · **Closed:** 2026-10-14 01:46:29 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

grok-muse: create the `grok_explicit_instructions` sunset flag, plus `muse_explicit_instructions` if the Muse spike passed. Grok's `--rules` carries the full root bundle, and memory v2 is set per decision. Muse gets the bundle as its prompt prefix without `--trust-workspace`, or is declared legacy with no flag. Interrupt and wait reconstruction never nests a second bundle.

## Notes

[2026-10-14T04:42:24Z · sase-1ko.9] PROPOSED FOLLOW-UP: Fix the clean-base failure in test_render_failure_notifies_once (it patches notify_instruction_fallback on _instruction_boundary though the function is locally imported from instruction_delivery); triage the 20 unrelated TUI/fakey failures from ToolRun 6b4592878d13d109d663db0ab1cfdca9.

[2026-10-14T05:21:30Z · sase-1ko.9--1] PROPOSED FOLLOW-UP: Resolve the KNOWN Symvision private import `_RunManifest` in src/sase/instructions/manifests.py; the defining and importing files are unchanged in sase-1ko.9. ToolRun b7c895a6fb9509eeb26379723c33b46b labels it KNOWN (untouched). The earlier cross-file private-import cleanup and verification are recorded in sase-1ko.4 notes #1 and #5-6.

[2026-10-14T05:46:04Z · sase-1ko.9--1] PROPOSED FOLLOW-UP: ToolRun b7c895a6fb9509eeb26379723c33b46b had 22 failing tests under tests/ace/tui/widgets plus test_render_failure_notifies_once; all TUI failures are outside the Grok/Muse diff, and 15 exact TUI failures recur from ToolRun 6b4592878d13d109d663db0ab1cfdca9 (already recorded in note #1). The instruction test trace is the same pre-existing _instruction_boundary.notify_instruction_fallback patch-target failure recorded in note #1. Scoped pytest otherwise passed 55,622 tests.

[2026-10-14T05:46:29Z · sase-1ko.9--1] Grok/Muse explicit-delivery flags and adapter paths are implemented; the closed-bead epic-symbol was removed and sase bead epic-symbols reports none. just fmt passed. sase tool run check completed with 55,622 passed and exited 1 on one KNOWN _RunManifest Symvision item, 22 recurring unrelated ACE/TUI failures, and the recorded clean-base test_render_failure_notifies_once failure; follow-ups are recorded on this bead.

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.9.md) | [sase-1ko.9](sase-1ko.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8847d07`](https://github.com/sase-org/sase/commit/8847d07a086b9e930f1a787425ec4c3272ea6824) | feat(instructions): add Grok and Muse explicit delivery | [sase-1ko.9](sase-1ko.9.md) | 2026-10-14 04:42:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kj.8.1.land--3][1] | Verify the active phase still owns the Symvision helper allowances | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1kj.8.1.land.md

<!-- sase:referenced-by:end -->
