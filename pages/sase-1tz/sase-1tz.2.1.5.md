# Bead: sase-1tz.2.1.5 — Bound inventory\_build with reuse, an incremental history cache, and scoped queries

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.5` · **Size:** medium
**Created:** 2026-11-19 11:13:27 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_inventory: build the hood inventory once per project per tick instead of once per batch. Cache parsed primary-history trailers by HEAD and parse only new commits. Scope index and dismissed-record queries to the requested hoods, and give inventory_build its own deadline slice.

## Dependencies

- **Depends on:** [sase-1tz.2.1.3](sase-1tz.2.1.3.md) ◐ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.4](sase-1tz.2.1.4.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.5/README.md) | [sase-1tz.2.1.5](sase-1tz.2.1.5.md) | 0 |
