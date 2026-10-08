# Bead: sase-1i5.9.1 — Publish sase-core and sase, then raise plugin floors

[Bead Pages](../README.md) / [sase-1i5.9](sase-1i5.9.md) / sase-1i5.9.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1i5.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.md) · **Assignee:** `sase-1i5.9.1.land`
**Created:** 2026-10-08 14:37:02 EDT
**Plan:** [202610/release\_sase\_core\_and\_plugin\_floors.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_sase_core_and_plugin_floors.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/release_sase_core_and_plugin_floors.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/release_sase_core_and_plugin_floors.md

<!-- sase:links:end -->

## Description

A complete sase-core-rs release whose tag contains the commit in sase sase-core-revision.txt is on PyPI, sase master Master Gate is green and Full CI is fresh-green, ci_watch publishes sase against that floor, plugin floors that do not resolve are raised and published, and sase-10d plus phase bead sase-1i5.9 are closed done. Parent epic sase-1i5 stays open for its land agent.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.9.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1i5.9.1.land/README.md) | [sase-1i5.9.1](sase-1i5.9.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1i5.9.1.1--1][1] | epic decisions and plan | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.1.md

<!-- sase:referenced-by:end -->
