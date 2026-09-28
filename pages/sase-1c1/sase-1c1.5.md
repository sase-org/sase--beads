# Bead: sase-1c1.5 — Settle %tab completion fallout

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.5` · **Size:** medium
**Created:** 2026-09-28 07:09:29 EDT · **Closed:** 2026-09-28 07:21:38 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

tab-completion: decide whether the default main tab group is a leak when the agent_tabs flag is off, fix the product or the 11 agent/directive completion tests to match, and assert removed directive names explicitly.

## Notes

[2026-09-28T11:21:38Z · sase-1c1.5] Flag-off main-tab leak fixed in _build_tab_completion_candidates behind agent_tabs_enabled; 2 directive tests assert removed names absent with %tab present; new flag-gating test added. 40 passed in test_agent_completion + directive candidates; 46 parity/prompt/visibility and 35 interaction suites green; ruff check+format clean.

## Dependencies

- **Blocks:** [sase-1c1.12](sase-1c1.12.md) ◐ · ⧖ 2026-09-28
- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1c1.5/README.md) | [sase-1c1.5](sase-1c1.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1c1.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1c1.5/README.md

<!-- sase:referenced-by:end -->
