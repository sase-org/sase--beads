# Bead: sase-16z.8 — CLI capability cache for usage probes

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.8` · **Size:** medium
**Created:** 2026-09-23 11:06:17 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

capability-cache: add a fingerprint-keyed, TTL-bounded on-disk cache of CLI version and help capability results so warm Claude probes spawn 2 processes instead of 5, and agy/grok skip `--version` spawns. Invalidate an entry on fingerprint change, TTL expiry, or a drift/unsupported-version result.

## Dependencies

- **Depends on:** [sase-16z.5](sase-16z.5.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.8/README.md) | [sase-16z.8](sase-16z.8.md) | 0 |
