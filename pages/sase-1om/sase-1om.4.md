# Bead: sase-1om.4 — The sase agent load command and shared capacity view model

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.4` · **Size:** medium
**Created:** 2026-10-26 20:19:45 EDT · **Closed:** 2026-10-27 01:34:27 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

load-cli: a TUI-free view model (holders, live rows holding nothing grouped by reason, queued rows with real blockers, diagnostics) rendered by a new `sase agent load [-j]` command, plus a Reference section listing what holds capacity.

## Notes

[2026-10-27T05:34:27Z · sase-1om.4] load-cli done: shared capacity view model (src/sase/core/runner_slots/_capacity_view.py) + sase agent load [-j] [-r] (src/sase/agents/cli_load.py, parser, handler) + What-holds-capacity docs + regenerated CLI reference. Verified: sase tool run check green (all lint incl. symvision/mypy + scoped tests incl. 13 new test_agent_load_cli + fixed parser help test). Live athena output reads 7 of 8 with ACE override provenance; screenshot shape gives 5 of 8, six accounting entries, invalid->blocked, stale and over-limit lines covered.

## Dependencies

- **Depends on:** [sase-1om.3](sase-1om.3.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1om.9](sase-1om.9.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1om.4/README.md) | [sase-1om.4](sase-1om.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`78f60cd`](https://github.com/sase-org/sase/commit/78f60cd602e7d416bce656952dddd7fec72b87a3) | feat(agent): add sase agent load capacity view command | [sase-1om.4](sase-1om.4.md) | 2026-10-27 01:36:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1om.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1om.4/README.md

<!-- sase:referenced-by:end -->
