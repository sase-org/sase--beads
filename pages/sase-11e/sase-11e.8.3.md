# Bead: sase-11e.8.3 — Resolve automation tribe aliases and collisions in Rust

[Bead Pages](../README.md) / [sase-11e.8](sase-11e.8.md) / sase-11e.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11e.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11e.land.md) · **Assignee:** `sase-11e.8.3` · **Size:** medium
**Created:** 2026-09-16 01:04:13 EDT · **Closed:** 2026-09-16 03:43:13 EDT
**Plan:** [202609/axe\_routine\_job\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_routine_job_landing_repairs.md)

## Description

tribe_identity: preserve stored chop identity while exposing job consistently and rejecting independent job tribe collisions through shared core behavior.

## Notes

[2026-09-16T07:43:13Z · sase-11e.8.3] Implemented shared Rust/Python agent-tribe job/chop alias resolution, collision diagnostics, metadata preservation, query/panel behavior, and tests. Verified with cargo test -p sase_core agent_tribe --lib; focused pytest slices for tribe display, assignments, queries, core scan facade, and output-variable metadata; main just check; linked sase-core just check with PYO3_PYTHON and LD_LIBRARY_PATH set for Python 3.14.

## Dependencies

- **Depends on:** [sase-11e.8.2](sase-11e.8.2.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11e.8.4](sase-11e.8.4.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.8.3/README.md) | [sase-11e.8.3](sase-11e.8.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e4700fd`](https://github.com/sase-org/sase/commit/e4700fd747fae7a048835cc086a92b516606dc05) | feat(agent-tribes): route job alias behavior through core | [sase-11e.8.3](sase-11e.8.3.md) | 2026-09-16 03:45:02 EDT |
| sase-core | [`sase-core@ad13940`](https://github.com/sase-org/sase-core/commit/ad13940a3e1e658a1e17827e3ad3320d78561554) | feat(agent-tribes): add job alias core bindings | [sase-11e.8.3](sase-11e.8.3.md) | 2026-09-16 03:47:23 EDT |
