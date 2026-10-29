# Bead: sase-1pn.1 — Refuse cross-session messages into SASE Claude agents (sase-163)

[Bead Pages](../README.md) / [sase-1pn](README.md) / sase-1pn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.land.md) · **Assignee:** `sase-1pn.1` · **Size:** small
**Created:** 2026-10-29 10:44:08 EDT · **Closed:** 2026-10-29 11:53:46 EDT
**Plan:** [202610/task\_backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_2.md)

## Description

claude-isolation: make ClaudeCodeProvider launches refuse cross-session inbound messages and apply the claude_tools decision to the vendor async tools, with a provider-args regression test.

## Notes

[2026-10-29T15:53:21Z · sase-1pn.1] TASK RESOLVED: sase-163 — Claude launches now refuse cross-session inbound messages while preserving existing hook settings, deny ListAgents/Workflow/Monitor/CronCreate/CronDelete/RemoteTrigger plus ScheduleWakeup, and retain SendMessage. Stream peer-origin events are written to peer_messages.jsonl. Focused provider tests: 34 passed, 1 skipped. sase tool run check 208fd42bf81678b575deb0cfd0e7e470 passed lint/validation but exited 1 in scoped tests with verdict no_new_failures (2 KNOWN, 1 FLAKY); the failing tests are monitor-start/contract-manifest coverage tracked by sase-1pg, sase-1pi, and sase-1pj.2.1, unrelated to these provider changes.

[2026-10-29T15:53:46Z · sase-1pn.1] Implemented and verified Claude inbound refusal, async tool denial, and peer-origin artifact tripwire; focused tests 34 passed/1 skipped. check lint/validation passed; scoped tests reported no_new_failures (2 KNOWN, 1 FLAKY) documented on phase note.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pn.1/README.md) | [sase-1pn.1](sase-1pn.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pn.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1pn.3--1][2] | Need close note format from sibling phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pn.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.3.md

<!-- sase:referenced-by:end -->
