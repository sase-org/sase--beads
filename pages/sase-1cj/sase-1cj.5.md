# Bead: sase-1cj.5 — Off-thread prediction corpus warm cache for the TUI

[Bead Pages](../README.md) / [sase-1cj](README.md) / sase-1cj.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.2x` · **Assignee:** `sase-1cj.5` · **Size:** medium
**Created:** 2026-09-29 07:14:31 EDT · **Closed:** 2026-09-29 11:45:14 EDT
**Plan:** [202609/prompt\_next\_word\_prediction.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_next_word_prediction.md)

## Description

prediction-cache: build history rows (origin, project, cancelled), compile the history and session corpora off-thread next to the history-word warm job, swap them in atomically, compose the model, and give widgets a non-blocking predict accessor that degrades to silence.

## Notes

[2026-09-29T15:44:51Z · sase-1cj.5] PROPOSED FOLLOW-UP: check gates that fail identically on the clean base tree — lint(feature flags) rule 8 live bead sase-1be key agent_tabs (already noted on sase-1cj.1/.2/.4), patch/stitch terminology hits confined to sase-core fixture bytes, and tests test_load_agents_from_disk_uses_artifact_index_for_initial_tier + test_viewport_window_keeps_tier1_caps + test_bounded_agents_viewport_expands_near_prefix_end (all base-verified, unrelated areas)

[2026-09-29T15:45:14Z · sase-1cj.5] prediction-cache done and verified: history rows/token/project-resolver module, off-thread history+session warm mixin with atomic swap and session pruning, widget predict accessor with in-memory delete post-filter and session-disable-on-error, submit hook feeding the session source. Verified: 28 new tests pass (rows/token/swap/session/project/degrade/no-disk-IO), related suites green (66 history+core, 36 completion, 1288 history/core/actions, 5916 widgets), ruff+mypy+symvision+toobig+changelog+pyscripts+test-waits+plans+sase-validate clean; epic-symbols clean (Corpus/Model consumed here, candidates re-keyed to sase-1cj.7, rank re-keyed to sase-1cj.8). Remaining check failures reproduce identically on base and are recorded as follow-ups.

## Dependencies

- **Blocks:** [sase-1cj.10](sase-1cj.10.md) ◐ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.2](sase-1cj.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cj.4](sase-1cj.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.6](sase-1cj.6.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.8](sase-1cj.8.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cj.9](sase-1cj.9.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cj.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cj.5/README.md) | [sase-1cj.5](sase-1cj.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8f3b5bf`](https://github.com/sase-org/sase/commit/8f3b5bf6560162d54e7ccbc173eabac1665c6713) | feat(prediction-cache): off-thread prediction corpus warm cache for the TUI | [sase-1cj.5](sase-1cj.5.md) | 2026-09-29 11:46:55 EDT |
