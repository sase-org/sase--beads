# Bead: sase-1io.7 — Fix the read-model cache race, cut sase-core-rs, and ship sase v0.18.0

[Bead Pages](../README.md) / [sase-1io](README.md) / sase-1io.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.land.md) · **Assignee:** `sase-1io.7.land`
**Created:** 2026-10-09 06:48:48 EDT
**Plan:** [202610/finish\_release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_release_v0_18_0.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md

<!-- sase:links:end -->

## Description

The sase-core read-model cache survives concurrent readers and writers on every platform, a sase-core-rs release carrying every binding sase needs is complete on PyPI, Master Gate and Full CI are green on the sase master tip, release PR 299 merges, and `pip install sase==0.18.0` works from PyPI.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.land/README.md) | [sase-1io.7](sase-1io.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1io.7.1][1] | Need parent epic decisions | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.1/README.md

<!-- sase:referenced-by:end -->
