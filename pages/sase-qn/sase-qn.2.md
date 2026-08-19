# Bead: sase-qn.2 — Latest-version enrichment that scales with installed count, not catalog size

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.2` · **Size:** medium
**Created:** 2026-08-18 20:12:39 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

enrich: remove the quadratic installed-version lookup, scope eager PyPI enrichment to installed entries, add a lazy per-entry latest fetch for the highlighted row, bound the fetch budget, and prune the unbounded latest cache.

## Dependencies

- **Depends on:** [sase-qn.1](sase-qn.1.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.5](sase-qn.5.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.2/README.md) | [sase-qn.2](sase-qn.2.md) | 0 |
