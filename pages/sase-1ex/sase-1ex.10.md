# Bead: sase-1ex.10 — Explicit prompt-active state and one prompt-bar accessor

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.10` · **Size:** medium
**Created:** 2026-10-02 14:53:56 EDT · **Closed:** 2026-10-02 21:44:54 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

prompt-active-state: track the active prompt bar explicitly on the app so `_prompt_input_active()` no longer queries the DOM. Route every `#prompt-input-bar` and `PromptInputBar` lookup through one accessor, which is the prerequisite for a hidden spare bar.

## Notes

[2026-10-03T01:44:32Z · sase-1ex.10--1] PROPOSED FOLLOW-UP: just check lint (feature flags) fails identically on the clean base tree: closed flag bead sase-1ey still has a surviving three_pane_splits definition (src/sase/feature_flags/registry.py plus pager/deck usages); none of those paths are touched by this phase (git diff HEAD is empty for them)

[2026-10-03T01:44:54Z · sase-1ex.10--1] prompt-active-state done: single mounted_prompt_bar() accessor in _prompt_bar_stash_store.py, all call sites routed through it; fixed mount-mixin self-sufficiency bug found by test_prompt_bar_submit_no_cancel_save (4 failures, now green). Verified: 27 passed across test_prompt_active_explicit_state/submit_no_cancel_save/history_requests/editor_suspend; ruff+mypy clean; just fmt clean; monitor just check passed fmt/keep-sorted/ruff/mypy/model-policy. Remaining lint (feature flags) failure for closed sase-1ey/three_pane_splits reproduces on clean base (untouched paths) and is recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.3](sase-1ex.3.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.10.md) | [sase-1ex.10](sase-1ex.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae16afe`](https://github.com/sase-org/sase/commit/ae16afe54850ff1eb04f8aa1a74be985f8023b5a) | feat(prompt): track active prompt bar explicitly with one accessor | [sase-1ex.10](sase-1ex.10.md) | 2026-10-02 21:46:17 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.10--1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.10.md

<!-- sase:referenced-by:end -->
