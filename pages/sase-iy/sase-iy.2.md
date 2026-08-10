# Bead: sase-iy.2 — Fix the deterministic prompt-catalog convergence hang in the PNG lane

[Bead Pages](../README.md) / [sase-iy](README.md) / sase-iy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xb/README.md) · **Assignee:** `sase-iy.2` · **Size:** medium
**Created:** 2026-08-10 11:01:31 EDT · **Closed:** 2026-08-10 12:46:47 EDT
**Plan:** [202608/retire\_sase\_ct\_umbrella.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_sase_ct_umbrella.md)

## Description

catalog: make the ACE startup prompt-catalog rebuild worker stop holding wait_for_visual_idle open for its full 30s deadline. Reproduced deterministically in isolation on clean master; fix it centrally in the visual fixtures rather than per file, and prove the PNG lane green.

## Notes

[2026-08-10T16:32:44Z · sase-iy.2] PROPOSED FOLLOW-UP: Symvision unused-public gate fails on resolve_notification_tab_icon — just check stops at lint (symvision) in untouched src/sase/ace/tui/widgets/notification_tab_style.py; decide whether to privatize/remove the API or whitelist it intentionally.

[2026-08-10T16:33:56Z · sase-iy.2] PROPOSED FOLLOW-UP: Committed plan validation fails on existing large tale plans — just validate-committed-plans reports 21 strict 202608 tale files with size=large; convert them to epics or resize to xsmall/small/medium.

[2026-08-10T16:46:12Z · wv.f4] DISCOVERED ISSUE: Independent reproduction while verifying the unrelated smarter_model_alias change on 2026-08-10. Full just test-visual queued behind existing holders, then ran 648 visual tests and failed 89 / passed 559 / skipped 1. Besides intentional Models-panel PNG drift from a new builtin alias row, many unrelated ACE prompt/completion/frontmatter visual tests timed out with pending_workers=[prompt-catalog:0], matching this phase prompt-catalog convergence hang. This remains a blocker for using full just test-visual as a clean verification lane until the active phase lands.

[2026-08-10T16:46:47Z · sase-iy.2] Verified central visual startup fixture disables prompt-catalog rebuild workers; prompt highlighting targeted 21 passed, startup guard targeted 1 passed, slow-tools targeted normal/contention 1 passed each, full just test-visual 648 passed/1 skipped, full just test-visual-contention 648 passed/1 skipped, ruff+mypy green, test-scoped 497 passed. just check rerun stops at unrelated Symvision resolve_notification_tab_icon failure; PROPOSED FOLLOW-UP notes recorded for Symvision and committed-plan validation.

[2026-08-10T16:48:23Z · sase-iy.2] Verified just test-visual (648 passed, 1 skipped), just test-visual-contention (648 passed, 1 skipped), just test-scoped (497 passed), ruff and mypy; just check still stops at unrelated Symvision issue already noted.

## Dependencies

- **Blocks:** [sase-iy.5](sase-iy.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-iy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-iy.2/README.md) | [sase-iy.2](sase-iy.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`128b326`](https://github.com/sase-org/sase/commit/128b326ea46a11c05ece35e8ff17d9d6b81a4bc0) | test: stabilize PNG visual prompt catalog fixtures | [sase-iy.2](sase-iy.2.md) | 2026-08-10 12:50:24 EDT |
