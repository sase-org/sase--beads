# Bead: sase-1ev.9 — Instructions group and instruction cards

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.9` · **Size:** medium
**Created:** 2026-10-02 14:43:16 EDT · **Closed:** 2026-10-03 03:10:57 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

instructions-group: add a collapsed INSTRUCTIONS rail group for AGENTS.md subjects with shim alias and diverged chips and the TEMPLATE chip for home. Their read-only cards show cause rows and the rendered body at now, and stepping, diff, the Timeline lens, and H all work.

## Notes

[2026-10-03T07:10:40Z · sase-1ev.9--1] PROPOSED FOLLOW-UP: just check run ac75c222ff93c574fa17c40547cc960a reports 15 KNOWN failures (verdict no_new_failures), all reproduced identically on the clean base tree via git stash (13x test_prompt_bar_editor_stack.py AttributeError _mounted_prompt_bar, 1x missing plan_publication_payload_batches binding, 1x symvision __getattr__ in xprompt/__init__.py). No duplicate task bead found; sase-10d is a related but distinct missing-binding cohort, not the same defect.

[2026-10-03T07:10:57Z · sase-1ev.9--1] INSTRUCTIONS rail group done and verified: 14 focused tests in tests/ace/tui/modals/test_memory_pane_instructions.py green (re-ran 14 passed), ruff and mypy clean on touched files, live subjects() probe OK (4 instruction subjects resolve with annotated summaries and bodies). just check run ac75c222ff93c574fa17c40547cc960a verdict no_new_failures: its 15 KNOWN failures reproduce identically on the clean base tree (verified via git stash rerun) and are recorded as a PROPOSED FOLLOW-UP note; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1ev.12](sase-1ev.12.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ev.8](sase-1ev.8.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.9.md) | [sase-1ev.9](sase-1ev.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d854842`](https://github.com/sase-org/sase/commit/d854842e893bacf6285b2ef5cd21d5b596f7500e) | feat(memory-history): collapsed INSTRUCTIONS rail group and instruction cards (sase-1ev.9) | [sase-1ev.9](sase-1ev.9.md) | 2026-10-03 03:12:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.9--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.9.md

<!-- sase:referenced-by:end -->
