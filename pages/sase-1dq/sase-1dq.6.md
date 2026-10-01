# Bead: sase-1dq.6 — Mid-word autosuggest from the core word completion

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.6` · **Size:** medium
**Created:** 2026-09-30 16:38:28 EDT · **Closed:** 2026-10-01 03:37:57 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

midword-autosuggest: in auto mode, each typed word character requests complete_current_word. The UI composes suffix plus continuation as an inline ghost or peek, keeps silent on a core that lacks the field, filters deleted words, and guards keystroke latency with a measured synchronous-draft threshold and an off-pump deferred path.

## Notes

[2026-10-01T07:16:49Z · sase-1dq.6] PROPOSED FOLLOW-UP: tests/core/test_prompt_prediction_facade.py::test_replay_report_carries_midword_section fails identically on the clean base tree (Rust replay report.midword is None); untouched by this phase, needs an owner

[2026-10-01T07:37:30Z · sase-1dq.6--1] PROPOSED FOLLOW-UP: just check lint (symvision) still fails on 3 unused-public symbols that reproduce identically on the clean base tree (verified via worktree at HEAD 41b2bc5035, same exit 1, same 4 lines): HandoffSubmitResult, owner_ref (both already tracked by task bead sase-1dn), plus fit_next_word_ghost in next_word_completion.py (no src-internal caller on base; only tests + __all__ use it). 4th line StarterResolution is KNOWN with witness. None caused by this phase (diff adds callers/helpers only, touches no tool/ files).

[2026-10-01T07:37:57Z · sase-1dq.6--1] Mid-word autosuggest done and verified. Landed: NextWordMidwordMixin (auto trigger, suffix-plus-continuation ghost/peek composition, thin-timer + pump-free deferred path, mid-word peek accepts), plumbing in _file_completion_prediction.py, NextWordChain.midword + arm/explicit/refresh awareness, peek delegation, pure helpers in next_word_completion.py + next_word_midword_eligible. Verified: 23 new tests in test_prompt_next_word_midword.py pass, 52 total pass across midword/inline-tail/completion/placement suites, 2 goldens inspected (next_word_midword_ghost_120x40, next_word_midword_peek_120x40); mypy/ruff/fmt clean; stale Justfile --epic-symbol sase-1dq(PromptPredictionWordCompletion) removed (symbol now properly used); sase bead epic-symbols sase-1dq.6 clean. Residual just-check symvision failure (HandoffSubmitResult, owner_ref, fit_next_word_ghost) reproduces identically on clean base tree and is filed as PROPOSED FOLLOW-UP (tool symbols tracked by sase-1dn); facade replay-report midword test failure likewise pre-existing per prior note.

## Dependencies

- **Depends on:** [sase-1dq.2](sase-1dq.2.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1dq.5](sase-1dq.5.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dq.7](sase-1dq.7.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1dq.6.md) | [sase-1dq.6](sase-1dq.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e2cec53`](https://github.com/sase-org/sase/commit/e2cec539ef49d0bf7edacd9e17f9f458880c4119) | feat(ace): add next-word midword ghost completion and peek display | [sase-1dq.6](sase-1dq.6.md) | 2026-10-01 04:11:29 EDT |
