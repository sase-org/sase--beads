# Bead: sase-1vb.3 — Clear the four globals that fail the test-cost leak gate

[Bead Pages](../README.md) / [sase-1vb](README.md) / sase-1vb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ge](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ge.md) · **Assignee:** `sase-1vb.3` · **Size:** medium
**Created:** 2026-11-26 06:30:37 EST · **Closed:** 2026-11-26 07:25:48 EST
**Plan:** [202611/green\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202611/green_github_actions.md)

## Description

leak-gate: fix the four leaking module globals at their root so the CI Telemetry global-leak blocking gate reports zero poisoning changes.

## Notes

[2026-11-26T12:25:07Z · sase-1vb.3] PROPOSED FOLLOW-UP: Triage the scoped-check failure of tests/ace/tui/test_refresh_warmup_gc.py::test_auto_refresh_merge_live_hints_and_warmup_release_obsolete_payloads, which retained one FinalizerInventoryWorkerResult; existing flake bead sase-1v2 tracks the same assertion. One serial run on the clean base passed, so this run did not reproduce there.

[2026-11-26T12:25:48Z · sase-1vb.3] Isolated warn-once and skip-streak state and released projected detail ownership; 613-target and post-fix 153-test test-cost runs had zero poisoning, and Symvision passed. Full just check passed all lint/policy stages but stopped on the already-tracked sase-1v2 refresh-warmup FinalizerInventoryWorkerResult flake; one clean-base serial rerun passed. Epic-symbol check was clear.

## Dependencies

- **Blocks:** [sase-1vb.6](sase-1vb.6.md) ◐ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.3/README.md) | [sase-1vb.3](sase-1vb.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`102e579`](https://github.com/sase-org/sase/commit/102e579e2aaa6b88bdf672985ff6a1077719c3bb) | fix(tests): isolate leaking test state | [sase-1vb.3](sase-1vb.3.md) | 2026-11-26 07:27:23 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vb.3][1] | Need the phase scope, design file, decisions, and prior notes before implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vb.3/README.md

<!-- sase:referenced-by:end -->
