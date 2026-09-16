# Bead: sase-11l.4 — sase agent hold command group

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.4` · **Size:** large
**Created:** 2026-09-15 22:46:02 EDT · **Closed:** 2026-09-16 13:00:57 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

hold-cli: add sase agent hold create/list/release/run/show plus arm and expiry notifications, proving the runtime behind a watchable CLI before any prompt surface exists.

## Notes

[2026-09-16T17:00:57Z · sase-11l.4] Implemented sase agent hold create/list/release/run/show, agent_hold_default_ttl/agent_hold_max_ttl config, and arm/release lifecycle notifications. Verified: just fix; just check (all lint gates incl. symvision/mypy/ruff green, full 42188-test scoped suite green); sase agent hold --help and per-subcommand --help render alphabetically ordered with short aliases; a real end-to-end create/list/show/release round trip against the Rust hold store; a real admission-integration test (tests/test_run_agent_runner_slot_capacity.py::test_real_agent_hold_parks_a_waiter_and_release_resumes_it) proving a held waiter parks and resumes after release; sase bead epic-symbols sase-11l.4 (no entries needed).

## Dependencies

- **Depends on:** [sase-11l.3](sase-11l.3.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11l.5](sase-11l.5.md) ◐ · ⧖ 2026-09-15
- **Blocks:** [sase-11l.7](sase-11l.7.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11l.8](sase-11l.8.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.4.md) | [sase-11l.4](sase-11l.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`520c7db`](https://github.com/sase-org/sase/commit/520c7dbf419d3847f941c0a1cb47e384b4f0cf6d) | feat(agent-hold): add the sase agent hold command group | [sase-11l.4](sase-11l.4.md) | 2026-09-16 13:02:32 EDT |
