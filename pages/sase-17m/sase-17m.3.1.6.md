# Bead: sase-17m.3.1.6 — Agent name registry session kinds and schema v3

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.6` · **Size:** small
**Created:** 2026-09-24 02:56:50 EDT · **Closed:** 2026-09-24 10:06:51 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

name-registry: agent_name_registry.json reservation_kind and container_kind become session, readers accept family, and SCHEMA_VERSION goes 2 to 3 through the existing legacy-upgrade and stale-cache rebuild path without moving a rebuild onto ACE startup or the UI thread.

## Notes

[2026-09-24T14:06:32Z · sase-17m.3.1.6] PROPOSED FOLLOW-UP: just check lint gate symvision fails identically on clean master (private-import reports across llm_provider/ace/history, none in name-registry files); needs triage before sase-17m.3.1.7 verify can go green

[2026-09-24T14:06:51Z · sase-17m.3.1.6] name-registry cutover done: writers store session kinds, readers accept family via is_agent_session_container_kind, schema v3 with v2 legacy upgrade plus stale-cache rebuild, core wire kinds normalized at apply boundary; verified 478 focused tests green (registry rebuild/reservations/claims/forced-reuse/bead cleanup/catalog/agents_sync) plus ruff and mypy clean; just check lint blocked by pre-existing symvision failure identical on clean master (see PROPOSED FOLLOW-UP note)

## Dependencies

- **Depends on:** [sase-17m.3.1.4](sase-17m.3.1.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.7](sase-17m.3.1.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.6/README.md) | [sase-17m.3.1.6](sase-17m.3.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`12b253c`](https://github.com/sase-org/sase/commit/12b253c35db43302c636c14f38fe769057c8b3e7) | refactor(agent-session): cut name registry to session kinds and schema v3 (sase-17m.3.1.6) | [sase-17m.3.1.6](sase-17m.3.1.6.md) | 2026-09-24 10:08:34 EDT |
