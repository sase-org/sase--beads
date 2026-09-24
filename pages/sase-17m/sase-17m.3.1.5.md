# Bead: sase-17m.3.1.5 — Durable Python-owned JSON surfaces

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.5` · **Size:** medium
**Created:** 2026-09-24 02:56:48 EDT · **Closed:** 2026-09-24 10:41:07 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

durable-json: saved dismissed groups (canonical_global_agent_session), wait_for_fork_sources and chat-fork source kind session, gate descriptors and gate_next_fork session, notification action_data agent_session_root_suffix, ops revert requests, launch-request agent_session_type, and stats runtime_group_by. Writers emit only new spellings; named legacy readers load pre-rename files.

## Notes

[2026-09-24T14:34:04Z · sase-17m.3.1.5] Verified: 8 durable-json surfaces write only agent-session spellings with named legacy readers (dismissed-group probe+wire, fork source kind session, gate next-fork session default+normalize, action_data agent_session_root_suffix, revert agent_session_base/session scope, launch agent_session_type+context keys, stats normalize_runtime_group_by, follows.json opaque keys). New tests/test_agent_session_durable_json.py 22/22 pass; focused suites green (gate/question/plan shells, revert, history fork+continuation, stats, handoff, notifications, monitor settlement, dismissed groups, extract_naming); ruff+mypy green; symvision flag set identical with and without this diff.

[2026-09-24T14:34:40Z · sase-17m.3.1.5] PROPOSED FOLLOW-UP: whole-repo just check is red on unmodified master from 73 pre-existing symvision private-import flags (llm_provider/usage, monitor, notification_gates/debug, etc., none in wire-cutover files; flag set byte-identical with and without the durable-json diff, verified via stash). Verify phase should confirm and route to the symvision whitelist owner.

[2026-09-24T14:41:07Z · sase-17m.3.1.5] Closed by explicit `sase stitch create -B close` after create_commit landed 5393b41b0 ("refactor(agent-session): durable Python-owned JSON surfaces emit session spellings (sase-17m.3.1.5)"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-17m.3.1.5` if more work remains.

## Dependencies

- **Depends on:** [sase-17m.3.1.4](sase-17m.3.1.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.7](sase-17m.3.1.7.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.5/README.md) | [sase-17m.3.1.5](sase-17m.3.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5393b41`](https://github.com/sase-org/sase/commit/5393b41b0de4df4912adb2fe53eff081eec45e51) | refactor(agent-session): durable Python-owned JSON surfaces emit session spellings (sase-17m.3.1.5) | [sase-17m.3.1.5](sase-17m.3.1.5.md) | 2026-09-24 10:36:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.3.1.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.5/README.md

<!-- sase:referenced-by:end -->
