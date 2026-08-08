# Bead: sase-hp.4 — Post-write follow-up actions with memory and skill init integration

[Bead Pages](../README.md) / [sase-hp](README.md) / sase-hp.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vy/README.md) · **Assignee:** `sase-hp.4` · **Size:** medium
**Created:** 2026-08-08 15:52:25 EDT · **Closed:** 2026-08-08 17:20:46 EDT
**Plan:** [202608/xprompt\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_target_mode.md)

## Description

followup: replace the single commit/push confirmation with a classifier-driven follow-up chooser that offers commit/push, a scoped chezmoi apply, `sase memory init`, or `sase skill init` — whichever actually apply to the written file — and runs them through the tracked task queue.

## Notes

[2026-08-08T21:20:46Z · sase-hp.4] Implemented classifier-driven post-write actions with memory/skill init, scoped chezmoi apply, and sequenced tracked tasks. Verified with just install; targeted pytest tests/xprompt/test_write_targets.py tests/ace/tui/actions/test_prompt_save_xprompt_git.py tests/ace/tui/actions/test_prompt_save_xprompt_targets.py tests/ace/tui/modals/test_post_write_actions_modal.py (28 passed); just check passed with scoped lane escalated to the full suite because of Justfile.

[2026-08-08T21:22:09Z · sase-hp.4] Verified with just install, focused pytest for write targets/post-write modal/prompt-save git paths, just _lint-symvision, and just check; final just check passed with the scoped lane escalating to the full suite because Justfile changed.

## Dependencies

- **Depends on:** [sase-hp.1](sase-hp.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hp.6](sase-hp.6.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.4/README.md) | [sase-hp.4](sase-hp.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d337a4e`](https://github.com/sase-org/sase/commit/d337a4edc215001e42cf7eb8736bba593366b381) | feat(xprompt): offer post-write follow-up actions | [sase-hp.4](sase-hp.4.md) | 2026-08-08 17:23:32 EDT |
