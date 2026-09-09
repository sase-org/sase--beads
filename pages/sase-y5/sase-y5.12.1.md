# Bead: sase-y5.12.1 — Re-implement scoped capacity hints and usage attention

[Bead Pages](../README.md) / [sase-y5.12](sase-y5.12.md) / sase-y5.12.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-y5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-y5.land.md) · **Assignee:** `sase-y5.12.1` · **Size:** medium
**Created:** 2026-09-09 06:11:32 EDT · **Closed:** 2026-09-09 07:56:16 EDT
**Plan:** [202609/usage\_context\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_context_recovery.md)

## Description

usage-context-rework: Restore the recovered usage-context modules, tests, and PNG goldens from the recovery artifact, adapt them to the post-flag-removal tree, and re-implement the lost picker, alias-detail, and indicator wiring they specify.

## Notes

[2026-09-09T11:56:16Z · sase-y5.12.1] Restored usage-context modules from file:explicit:762a0fcfad720e2b70a9331b, adapted them off provider_usage_metrics onto llm_provider.usage_metrics.enabled, re-exported provider_usage_window_applies/summarize_for_model, and rewired picker rows, alias detail, and the top-bar indicator. Verified: six recovered pytest files plus indicator unit tests (45 passed), two PNG suites after inspecting drift and regenerating goldens (2 passed), sase bead epic-symbols sase-y5.12.1 (no leftovers), and just check (lint + scoped tests).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.12.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.12.1/README.md) | [sase-y5.12.1](sase-y5.12.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cef06cd`](https://github.com/sase-org/sase/commit/cef06cdcad1c34723d9f1ce1d9c9bce013624fed) | feat(usage): restore scoped capacity hints and usage attention (sase-y5.12.1) | [sase-y5.12.1](sase-y5.12.1.md) | 2026-09-09 07:57:47 EDT |
