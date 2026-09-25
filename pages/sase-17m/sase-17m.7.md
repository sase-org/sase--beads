# Bead: sase-17m.7 — sase-telegram cutover

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.7` · **Size:** small
**Created:** 2026-09-23 22:46:40 EDT · **Closed:** 2026-09-25 00:42:24 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

telegram: move the /show session kind, formatting, help, docs, and tests to the renamed sase APIs, and stop a missing import from silently disabling the lookup.

## Notes

[2026-09-25T04:42:00Z · sase-17m.7--1] PROPOSED FOLLOW-UP: test_receiver_runtime mtime-only digest flakes (test_host_plugin_and_native_changes_each_new_generation, test_executable_replacement_changes_generation fail intermittently on clean HEAD; digest hashes path+size+mtime_ns, not content, so same-size rewrites collide)

[2026-09-25T04:42:24Z · sase-17m.7--1] Cut /show over to agent-session APIs (show_entities/show_format/agent_format/agent_show/commands, help, docs, tests); missing import now raises instead of silently disabling lookup. Verified: ruff clean, mypy clean (46 files), 271/271 show-scope tests pass, full suite 678 passed with only 2 pre-existing test_receiver_runtime mtime-digest flakes that fail intermittently on clean HEAD (recorded as PROPOSED FOLLOW-UP). No epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-17m.4](sase-17m.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.8](sase-17m.8.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.7.md) | [sase-17m.7](sase-17m.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.7--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.7.md

<!-- sase:referenced-by:end -->
