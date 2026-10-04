# Bead: sase-1fv.6 — Wire the existing path into the snippet flow

[Bead Pages](../README.md) / [sase-1fv](README.md) / sase-1fv.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0w7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md) · **Assignee:** `sase-1fv.6` · **Size:** medium
**Created:** 2026-10-04 06:33:07 EDT · **Closed:** 2026-10-04 15:26:29 EDT
**Plan:** [202610/existing\_macro\_snippet\_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)

## Description

wire-snippet-existing: mirror the macro wiring in `_SnippetLocationFlow` using the provenance catalog, add replace-draft semantics to the snippet pane, refresh the hint label, and update the snippet authoring docs.

## Notes

[2026-10-04T19:00:46Z · sase-1fv.6] Verified: SnippetLocationFlow mirrors the mini-macro existing path (e → finder, editable load, plugin/built-in/macro-derived override picker + name modal, back/cancel/origin-loss, same-target Already editing, dirty confirm_discard). replace_draft keeps focus restore. Hint is new / edit snippet…. Docs keymap + authoring step 1. Live-flow PNG snippet_location_flow_finder_120x40.png inspected (3 matches: plugin help selected, todo active, todo shadowed). Targeted unit tests 80 passed; fix-tui-screenshots created finder golden, g-prefix unchanged (overlay truncated before gt). epic-symbols clean.

[2026-10-04T19:23:40Z · sase-1fv.6--1] PROPOSED FOLLOW-UP: unused-public KillProvenance in runner_kill_provenance.py (sase-1g0)

[2026-10-04T19:26:29Z · sase-1fv.6--1] Verified: SnippetLocationFlow mirrors the mini-macro existing path (e → finder, editable load, plugin/built-in/macro-derived override picker + name modal, back/cancel/origin-loss, same-target Already editing, dirty confirm_discard). replace_draft keeps focus restore. Hint is new / edit snippet…. Docs keymap + authoring step 1. Live-flow PNG snippet_location_flow_finder_120x40.png inspected (plugin help selected, todo active, todo shadowed). Privatized in-file _PickerPayload. Targeted unit tests 58 passed; workflow-package symvision clean; epic-symbols clean. just check still fails unused-public classify_runner_kill/KillProvenance in runner_kill_provenance.py (this phase did not touch that file; sase-1g0; recorded PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1fv.5](sase-1fv.5.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fv.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.6.md) | [sase-1fv.6](sase-1fv.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`807e0fa`](https://github.com/sase-org/sase/commit/807e0fa107173d0f9ec72343aea642eb014e125d) | feat(tui): wire existing-definition path into snippet location flow | [sase-1fv.6](sase-1fv.6.md) | 2026-10-04 15:27:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:51--3][1] | Understand whether this epic still owns the public symbols reported by Symvision | 1 |
| read-by | [agent:sase-1fv.4][2] | Need the open phase that will consume the snippet entry builder | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.51.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.4/README.md

<!-- sase:referenced-by:end -->
