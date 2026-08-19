# Bead: sase-qn.3 — Catalog fetch past GitHub search's 1000-result cap

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.3` · **Size:** medium
**Created:** 2026-08-18 20:12:39 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

fetch: shard the topic search so results above GitHub's hard 1000-item search cap are still returned, surface truncation and incomplete_results as catalog warnings, and make the gh timeout scale with page count instead of a flat 20 s.

## Dependencies

- **Depends on:** [sase-qn.1](sase-qn.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.5](sase-qn.5.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.3/README.md) | [sase-qn.3](sase-qn.3.md) | 0 |
