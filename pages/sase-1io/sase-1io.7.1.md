# Bead: sase-1io.7.1 — Make the sase-core read-model cache safe under concurrent access

[Bead Pages](../README.md) / [sase-1io.7](sase-1io.7.md) / sase-1io.7.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1io.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1io.land.md) · **Assignee:** `sase-1io.7.1` · **Size:** medium
**Created:** 2026-10-09 06:48:48 EDT
**Plan:** [202610/finish\_release\_v0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_v0_18_0.md)

## Description

core-cache-race: stop unlinking or implicitly recreating a live SQLite read-model cache, keep cache faults from failing mutations, prove it with a stress run, and drop the now-redundant lock_wait_ms golden helper.

## Dependencies

- **Blocks:** [sase-1io.7.4](sase-1io.7.4.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1io.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1io.7.1/README.md) | [sase-1io.7.1](sase-1io.7.1.md) | 0 |
