# Bead: sase-16h.3 — Make the wrapper as faithful as the raw command

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.3` · **Size:** medium
**Created:** 2026-09-22 13:05:41 EDT · **Closed:** 2026-09-22 16:03:57 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

wrapper-fidelity: keep the child in the wrapper's process group under a live owner, make an inline child die with its wrapper, reap identity-matched survivors of lost runs, and give the child one merged pipe whenever a single target receives both streams.

## Notes

[2026-09-22T19:56:32Z · sase-16h.3] PROPOSED FOLLOW-UP: symvision flags agent_env_refusal_reason in src/sase/service/platform.py as unused on clean master too — pre-existing just check red unrelated to wrapper-fidelity

[2026-09-22T20:03:57Z · sase-16h.3] wrapper-fidelity landed: owner children share the wrapper pg with no wrapper SIGKILL escalation; inline children get their own session plus a Linux parent-death signal; observe persists child pid/pgid/identity right after spawn fail-open; reconcile reap candidates are TERM-then-KILLed only with matching pg-leader identity, executor-only (queries never signal); merged single-pipe under owners or shared fds with compact keeping two pipes, documented in docs/tool.md with a show -l no-total-order note; Justfile sase-16h(tool_run_observe) whitelist removed and epic-symbols clean. Verified: new tests/tool/test_wrapper_fidelity.py (8 tests) pass; old-code probe reproduced both defects (regrouped out-block/err-block, orphan surviving group SIGKILL); neighbors green (58 files incl. executor/liveness/signals/ownership/store, then 85 across tests/tool plus smoke twin); sase tool run check gates all pass except symvision agent_env_refusal_reason, which fails identically on clean master (recorded as PROPOSED FOLLOW-UP). sase-16b/16d fix evidence (group-kill leaves no sh/sleep survivors; interleaved out/err order; stale-pgid no-signal) is in the new tests for the land agent.

## Dependencies

- **Depends on:** [sase-16h.2](sase-16h.2.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16h.4](sase-16h.4.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.3/README.md) | [sase-16h.3](sase-16h.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5950d06`](https://github.com/sase-org/sase/commit/5950d069c2c5f58f0f42ae2aafb0a8c2c35c0ec2) | feat(tool): wrapper-fidelity process groups, early observe, and orphan reaping | [sase-16h.3](sase-16h.3.md) | 2026-09-22 16:16:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16h.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.3/README.md

<!-- sase:referenced-by:end -->
