# Bead: sase-170.5 — Inherit remembered tribe and summary for new clan generations

[Bead Pages](../README.md) / [sase-170](README.md) / sase-170.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pw.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pw.w0.md) · **Assignee:** `sase-170.5` · **Size:** medium
**Created:** 2026-09-23 11:39:58 EDT · **Closed:** 2026-09-23 14:02:53 EDT
**Plan:** [202609/tribe\_clan\_summaries\_and\_clan\_records.md](https://github.com/sase-org/sase--plans/blob/main/202609/tribe_clan_summaries_and_clan_records.md)

## Description

clan_launch_defaults: when a launch creates a new generation of a previously recorded clan without explicit tribe or summary, inherit the remembered tribe, re-run the remembered summary script (falling back to the remembered text), record them as Inherited, log it, document it, and test it.

## Notes

[2026-09-23T18:02:09Z · sase-170.5] PROPOSED FOLLOW-UP: Fix pre-existing symvision unused-public ClanSummaryDigest in _agent_tribe_clan_summaries.py blocking just check (fails on clean tree at 69a5ca5e1)

[2026-09-23T18:02:53Z · sase-170.5] Inherited tribe/summary for new clan generations in run_agent_directives (_is_new check, inherited record+log, docs); 9 new tests pass, 17 wiring + clan-summary refresh suites green; epic-symbols clean; just check otherwise green except pre-existing symvision ClanSummaryDigest (recorded as follow-up)

## Dependencies

- **Depends on:** [sase-170.3](sase-170.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-170.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.5/README.md) | [sase-170.5](sase-170.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1fb9d01`](https://github.com/sase-org/sase/commit/1fb9d01385cbe420eaed7e3c341eb921ca178ba4) | feat(clans): inherit remembered tribe and summary for new clan generations | [sase-170.5](sase-170.5.md) | 2026-09-23 14:08:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-170.5][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.5/README.md

<!-- sase:referenced-by:end -->
