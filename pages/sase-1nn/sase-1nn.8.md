# Bead: sase-1nn.8 — Finish the sase v0.18.1 release blockers left by sase-1nn and watch it to PyPI

[Bead Pages](../README.md) / [sase-1nn](README.md) / sase-1nn.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.land.md) · **Assignee:** `sase-1nn.8.land`
**Created:** 2026-10-23 18:32:22 EDT
**Plan:** [202610/v0\_18\_1\_release\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_1_release_landing.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md

<!-- sase:links:end -->

## Description

Master Gate and Full CI are green on a tip that contains the custom-gate resize wait fix, the hermetic TUI profiling env, and an exact sase-core-rs 0.42.3 pin; ci_watch merges release PR #321; Publish uploads sase 0.18.1 to PyPI; and the lander that observes it records the evidence artifact and closes this epic and sase-1nn.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.land/README.md) | [sase-1nn.8](sase-1nn.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nn.8.1][1] | Need parent epic scope, decisions, plan | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.1/README.md

<!-- sase:referenced-by:end -->
