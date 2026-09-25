# Bead: sase-18f.9 — Verify green check and full test suite on clean master

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.9` · **Size:** small
**Created:** 2026-09-24 17:19:04 EDT · **Closed:** 2026-09-24 22:35:27 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

verify-green: on a clean checkout of latest master, prove that `sase tool run check` exits 0 and that the full non-visual `just test` passes except for baseline flakes. Fix only small stragglers from concurrent landings and record the rest as follow-ups.

## Notes

[2026-09-25T02:35:11Z · sase-18f.9] PROPOSED FOLLOW-UP: 34 test failures reproduce on clean master (query_profile_agents, completion snapshot/build/kind_coverage, family-kind/%id(family=) launch+kill-and-edit tests, ace/tui family relaunch) — caused by the agent-session query dialect / rename landings (3a1d0bab2, 543d01220); need a repair phase in that epic. Also: I fixed sase_core_wheel_cache mypy, a test-wait pragma, stale sase-18i epic-symbols, and two symvision unused publics (uncommitted in workspace).

[2026-09-25T02:35:27Z · sase-18f.9] Fixed stragglers (wheel-cache mypy, test-wait pragma, stale sase-18i epic symbols, 2 symvision publics); all lint stages pass. Full test run: 47119 pass, 34 fail, reproduced on clean master (agent-session dialect landings) - recorded as PROPOSED FOLLOW-UP, not green.

## Dependencies

- **Depends on:** [sase-18f.1](sase-18f.1.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.2](sase-18f.2.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.3](sase-18f.3.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.4](sase-18f.4.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.5](sase-18f.5.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.6](sase-18f.6.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.7](sase-18f.7.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-18f.8](sase-18f.8.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.9/README.md) | [sase-18f.9](sase-18f.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`561e4b6`](https://github.com/sase-org/sase/commit/561e4b6dd51549f0239dbe9a263d519974bb95b1) | fix(check): clear lint stragglers from concurrent landings | [sase-18f.9](sase-18f.9.md) | 2026-09-24 22:36:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.land][1] | Need green-check phase status and notes before routing mypy failure | 1 |
| read-by | [agent:sase-18f.9][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.9/README.md

<!-- sase:referenced-by:end -->
