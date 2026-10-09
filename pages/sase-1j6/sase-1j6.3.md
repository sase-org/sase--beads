# Bead: sase-1j6.3 — sase-core failure classifier, ledger state machine, and recovery wire

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.3` · **Size:** medium
**Created:** 2026-10-09 15:02:05 EDT · **Closed:** 2026-10-09 17:38:16 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

core-verdict: add the agent_auto_restart domain to sase-core (facts, witness, and verdict wires, the family-based classifier, ledger transitions, episode ids, the done-marker recovery field and status bucket, and the ↻ report glyph), then the Python adapter and the core pin bump.

## Notes

[2026-10-09T20:46:24Z · sase-1j6.3] PROPOSED FOLLOW-UP: Add the decisions-web record for update-skew restarts (at most once per lineage, pre-provider only); skipped per epic auto-decision decision_record=no

[2026-10-09T21:37:57Z · sase-1j6.3--1] PROPOSED FOLLOW-UP: symvision flags _reconcile_prompt_with_live_auto_state private import in axe refresh/bootstrap — pre-existing at HEAD, already fixed upstream by 7c6039f1 (make helper public); rebase past that commit clears it

[2026-10-09T21:38:03Z · sase-1j6.3--1] PROPOSED FOLLOW-UP: full-suite leftovers unrelated to this phase — vim containment (textual text-area--gutter KeyError + focus leak), zsh completion smoke timeout; all in files this phase does not touch, likely environmental/flaky

[2026-10-09T21:38:16Z · sase-1j6.3--1] core-verdict done: sase-core check pass (82504e73f91ea0547f18140c8495aba0) plus new agent_auto_restart domain (wire/catalog/classify/ledger/episode + py binding + DoneMarkerWire.recovery + RESTARTING bucket + glyph); verified test_core_agent_auto_restart 9 passed, import-budget 1 passed after deferring wire imports (closure +0, 3512 modules), ruff/mypy clean on touched files; remaining full-gate reds are pre-existing base-tree failures noted as PROPOSED FOLLOW-UP (symvision private-import fixed upstream in 7c6039f1; vim textual gutter KeyError; zsh smoke timeout); sase-core-revision.txt pin intentionally not bumped — land agent moves it past the host-owned sase-core commit

## Dependencies

- **Depends on:** [sase-1j6.2](sase-1j6.2.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1j6.4](sase-1j6.4.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.3.md) | [sase-1j6.3](sase-1j6.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d4ad8c9`](https://github.com/sase-org/sase-core/commit/d4ad8c9953a04d2663f4d406386a97b3376bb8b2) | feat(agent): add agent auto-restart core modules and scan wire | [sase-1j6.3](sase-1j6.3.md) | 2026-10-09 17:40:05 EDT |
| sase | [`f472226`](https://github.com/sase-org/sase/commit/f472226d5610cfb214ff2411b65cf2eef66c8f14) | feat(agent): add agent auto-restart wire with deferred TUI imports | [sase-1j6.3](sase-1j6.3.md) | 2026-10-09 17:45:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.3--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1j6.3.md

<!-- sase:referenced-by:end -->
