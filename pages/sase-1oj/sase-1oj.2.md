# Bead: sase-1oj.2 — Self-heal the corrupt bead read-model cache

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.2` · **Size:** medium
**Created:** 2026-10-26 16:07:27 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

## Description

core-read-model-heal: in sase-core's bead read model, classify SQLITE_CORRUPT write faults and repair them by REINDEX or an in-place table recreate. Stop swallowing invalidation failures, back off after failed rebuilds, never downgrade a newer cache, and add a regression test that reproduces athena's corrupt meta index.

## Dependencies

- **Blocks:** [sase-1oj.3](sase-1oj.3.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1oj.4](sase-1oj.4.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.2/README.md) | [sase-1oj.2](sase-1oj.2.md) | 0 |
