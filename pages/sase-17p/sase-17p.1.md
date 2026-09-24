# Bead: sase-17p.1 — Extend the sase-core ToolRun contract for reservation, adoption, and owner-aware settlement

[Bead Pages](../README.md) / [sase-17p](README.md) / sase-17p.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qj.md) · **Assignee:** `sase-17p.1` · **Size:** large
**Created:** 2026-09-24 08:40:20 EDT · **Closed:** 2026-09-24 10:57:35 EDT
**Plan:** [202609/tool\_e2\_durable\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e2_durable_handoff.md)

## Description

core-contract: add reservation with a private launch envelope, an atomic claim, a durable stop request, typed terminal causes, persisted finish diagnostics, the owner log locator, and owner-aware reconcile to the sase-core ToolRun store and bindings, all additive at wire schema 1, then move sase's core revision pin.

## Notes

[2026-09-24T14:06:48Z · sase-17p.1--1] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past the sase-core tool_run_claim/tool_run_request_stop commit before sase-17p.2 lands — CI's pinned-bindings check fails on the new adapters until then. Checked 2026-09-24: no commit in sase-core (local or origin/master) contains tool_run_claim; bindings exist only as uncommitted working-tree changes, so the pin stays at ae9dbf6e0719. Phase standalone-handoff must ratchet first.

[2026-09-24T14:07:00Z · sase-17p.1--1] PROPOSED FOLLOW-UP: close sase-145 — acceptance verified in sase-17p.1 (tests/tool/test_executor.py::test_finish_diagnostics_persist_spawn_and_truncation shows spawn-127 and truncation diagnostics in sase tool show RUN -j diagnostics, plus unit coverage of log_write_diagnostics for write-failed sinks; src/sase/tool/executor.py now passes ingest+truncation+log-write facts to finish_tool_run).

## Dependencies

- **Blocks:** [sase-17p.2](sase-17p.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17p.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17p.1.md) | [sase-17p.1](sase-17p.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b6b9f4f`](https://github.com/sase-org/sase/commit/b6b9f4f59b900f74edbcd0bbea2f704c2659a128) | feat(tool): add hand-off adapters, contract probes, and finish diagnostics | [sase-17p.1](sase-17p.1.md) | 2026-09-24 10:44:13 EDT |
| sase-core | [`sase-core@9956773`](https://github.com/sase-org/sase-core/commit/9956773f1fee51305700b0a1e5004873dbc36e5c) | feat(tool-run): add reservation, claim, stop requests, and owner-aware settlement | [sase-17p.1](sase-17p.1.md) | 2026-09-24 10:47:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17p.land][1] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17p.land/README.md

<!-- sase:referenced-by:end -->
