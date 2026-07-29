# Bead: sase-au.3 — Python statistics models and builder for the XPrompts view

[Bead Pages](../README.md) / [sase-au](README.md) / sase-au.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-au.3` · **Size:** medium
**Created:** 2026-07-29 16:26:24 UTC · **Closed:** 2026-07-29 16:40:06 UTC
**Plan:** [202607/xprompt\_statistics.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_statistics.md)

## Description

py-stats: add the XPrompts view models, payload builder, and query request knobs to sase.stats so the view is built from the agreed payload contract, degrades to an explicit unavailable state when the section is missing, and is covered by fixture-driven tests.

## Notes

[2026-07-29T16:40:06Z · sase-au.3] Implemented XPrompt request controls, immutable view models, payload builder, display-name projection, focus propagation, and fixture coverage. Verified 29 targeted stats/query/pane-loading tests pass; formatting, Ruff, mypy, Symvision, toobig, and git diff checks pass. Full pytest: 23,695 passed and 7 skipped, with one unrelated reproducible failure in tests/main/test_task_handler_list.py. just check reaches SASE validation and is blocked by pre-existing missing reciprocal prompt links for xprompt_statistics.md and notification_release_report.md.

## Dependencies

- **Blocks:** [sase-au.4](sase-au.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-au.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-au.3/README.md) | [sase-au.3](sase-au.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6d99736`](https://github.com/sase-org/sase/commit/6d99736516c426d900faa813f2584336fb3cffdc) | feat(stats): add XPrompt statistics view models | [sase-au.3](sase-au.3.md) | 2026-07-29 16:40:55 |
