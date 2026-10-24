# Bead: sase-1nn.8.4.3 — Unblock both release gates, cut sase-core 0.42.5, and ship sase v0.18.1

[Bead Pages](../README.md) / [sase-1nn.8.4](sase-1nn.8.4.md) / sase-1nn.8.4.3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13x.md) · **Assignee:** `sase-1nn.8.4.3.land`
**Created:** 2026-10-24 16:37:48 EDT
**Plan:** [202610/v0\_18\_1\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_unblock.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/v0_18_1_release_unblock.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_unblock.md

<!-- sase:links:end -->

## Description

Master Gate and Full CI are green on master, a complete sase-core-rs release contains sase's source pin, ci_watch merges release PR 321, Publish uploads sase 0.18.1 to PyPI, and the lander that observes it retains clean-install evidence as an artifact before landing.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nn.8.4.3.land/README.md) | [sase-1nn.8.4.3](sase-1nn.8.4.3.md) | 0 |
