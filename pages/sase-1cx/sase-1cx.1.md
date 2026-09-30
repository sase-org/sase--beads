# Bead: sase-1cx.1 — sase-core starter scope, monitor join, and sync wait budget

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.1` · **Size:** large
**Created:** 2026-09-29 20:32:13 EDT · **Closed:** 2026-09-30 07:54:55 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Previously Closed

> ↺ Closed 2026-09-30T01:27:34Z · done
>
> (none)
>
> Reopened 2026-09-30T11:04:33Z by `sase bead open`

## Description

core-detach-join: in the linked sase-core checkout, add the ToolRun `starter` record for detached hand-off runs, the atomic `tool_run_join` / `tool_run_release_join` APIs, `continuation_mode` in the launch envelope, and the `tool_run_sync_wait_budget` policy, with migrations, bindings, fixtures, and tests.

## Notes

[2026-09-30T01:27:34Z · sase-1cx.1] core-detach-join verified: sase tool run check green in sase-core; new tests pass (handoff starter/join/release matrix, continuation round-trip, compat starter/join columns, duration budget pinned table, py bindings join/release/budget). Wire schema stays 1.

[2026-09-30T10:29:08Z · sase-1d6.2] UNLANDED PRIOR ATTEMPT: agent sase-1cx.1's completion note (bead note #1) describes verified sase-core work that NEVER LANDED. The host commit finalizer failed on the sase-core stitch with missing_bead_action (the pinned-sibling commit regression; fix is epic sase-1d6 phase sase-1d6.1). No commit from this run exists in sase or sase-core origin/master. Salvage held workspace sase_42 (claim ace(run)-260929_203400) read-only; nothing there was staged, committed, moved, or cleaned.

Attached patch (verified with git apply --check against a pristine checkout of the base SHA):
🔒 sase-1cx.1-core.patch
- repo: sase-core, base SHA 1e51ff3ce9c53ee1a4bc9f52c3642ac4eea8f423, 25 files, 88969 bytes (20 tracked tool_run-path modifications + 5 new tool_run/fixtures JSON files). sase side was clean.
- intended sase-core commit message: feat(tool-run): add detached starter scope, monitor join, and sync wait budget
- approved phase plan: plan:202609/core_detach_join.md

Instructions to the relaunched agent: apply onto current origin/master with git apply --3way, resolve any conflicts (master has moved), then RE-RUN verification in sase-core (sase tool run check plus the handoff/join/release/budget tests) instead of trusting the old note. Reuse the approved plan; do not re-plan from scratch.

[2026-09-30T11:05:28Z · sase-1d6.3] REOPENED: bead closed before its verified work landed (pinned-sibling commit regression). Fix is live on host (63bde575f0, sase 0.17.1+1852.g63bde57). Relaunched agent must apply the UNLANDED PRIOR ATTEMPT patches with git apply --3way, resolve conflicts against current master, and re-verify.

[2026-09-30T11:24:21Z · sase-1cx.1] PROPOSED FOLLOW-UP: sase plan propose crashes on a links inlet while artifact-link cutover is incomplete — uncaught RuntimeError from artifact_link_indexes_imported; recovery text names `sase artifact link import-indexes --apply fleet-capable-e2ce6f584527` for roles plans and research. Derivation swallows the same error; explicit inlet publish does not. Closed bead sase-10y tracked a related import-indexes wedge.

[2026-09-30T11:54:55Z · sase-1cx.1--1] sase tool run check green (f7a9f9dba0b313e0977ba7ee079aa013, 385s); starter/join/release matrix, continuation round-trip, compat starter/join columns, duration budget pinned table, py bindings join/release/budget verified. Wire schema stays 1.

## Attachments

- 🔒 sase-1cx.1-core.patch · text/plain · 86.8838 KiB (private attachment)

## Dependencies

- **Blocks:** [sase-1cx.3](sase-1cx.3.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.1.md) | [sase-1cx.1](sase-1cx.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cee9f49`](https://github.com/sase-org/sase-core/commit/cee9f49aa53ae21958280141d21014f7d44a67fe) | feat(tool-run): add detached starter scope, monitor join, and sync wait budget | [sase-1cx.1](sase-1cx.1.md) | 2026-09-30 07:56:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0ub--1][1] | Verify attachment span fix renders colored bead detail | 1 |
| read-by | [agent:sase-1cx.1--1][2] | continue approved plan implementation after sase-core gate passed | 1 |
| read-by | [agent:sase-1cx.land][3] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1d6.land][4] | Need salvage notes, reopen notes, and current status of the five recovered beads | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ub.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.1.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.land/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d6.land/README.md

<!-- sase:referenced-by:end -->
