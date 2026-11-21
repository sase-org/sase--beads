# Bead: sase-1ut.2 — Accepted-but-failed gate turns project as needing a human

[Bead Pages](../README.md) / [sase-1ut](README.md) / sase-1ut.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1et](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1et.md) · **Assignee:** `sase-1ut.2` · **Size:** medium
**Created:** 2026-11-21 09:19:55 EST · **Closed:** 2026-11-21 10:32:14 EST
**Plan:** [202611/gate\_turn\_carry\_and\_failed\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202611/gate_turn_carry_and_failed_execution.md)

## Description

failed-gate-attention: persist execution-failure facts on the gate member, project them with failure status and recovery commands in CLI and ACE, and optionally resurface dismissed failures.

## Notes

[2026-11-21T15:32:02Z · sase-1ut.2] PROPOSED FOLLOW-UP: tests/core/test_continuation_retention.py::test_plan_protects_live_continuation_ancestry_from_audit_probe fails identically on the clean base tree (verified via git stash) — pre-existing, unrelated to failed-gate-attention; needs a task bead and owner

[2026-11-21T15:32:14Z · sase-1ut.2] failed-gate-attention done: gate_execution_failure persisted on member (pid cleared), projected via runtime_json with needs_attention/recovery_commands, Stopped bucket + ✗ glyph/style/label, CLI list/show + ACE section render failure with resume/restart/cancel, Enter reuses recovery dialog, reclaim backfills + resurfaces once; verified: just lint clean, 9 new tests + member/reclaim/failure-outcome/audit/budget suites green, app-import cap raised +2,176 attributed (sase-1ut.2), continuation_retention failure pre-existing on clean base (see PROPOSED FOLLOW-UP)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ut.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ut.2/README.md) | [sase-1ut.2](sase-1ut.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0741134`](https://github.com/sase-org/sase/commit/07411341e330e09b7a1e6843ae6dc16dc8b88ca8) | feat(gate-turn): surface accepted-but-failed gates as needing a human | [sase-1ut.2](sase-1ut.2.md) | 2026-11-21 10:33:47 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ut.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ut.2/README.md

<!-- sase:referenced-by:end -->
