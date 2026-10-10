# Bead: sase-1io.7.6.4 — Fix the popped-pane catalog reload and ship sase v0.18.0

[Bead Pages](../README.md) / [sase-1io.7.6](sase-1io.7.6.md) / sase-1io.7.6.4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.7.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.7.6.land.md) · **Assignee:** `sase-1io.7.6.4.land`
**Created:** 2026-10-10 09:29:17 EDT
**Plan:** [202610/finish\_v0\_18\_0\_ship.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_v0_18_0_ship.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_v0_18_0_ship.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_v0_18_0_ship.md

<!-- sase:links:end -->

## Description

The plugins pane does not start a catalog load after it has been popped, Master Gate and Full CI are green on a master tip that contains that fix, release PR 299 merges, and `pip install sase==0.18.0` works from PyPI.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.6.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.6.4.land/README.md) | [sase-1io.7.6.4](sase-1io.7.6.4.md) | 0 |
