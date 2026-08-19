# Bead: sase-qx.1 — Provider-disable mode on the Rust wire

[Bead Pages](../README.md) / [sase-qx](README.md) / sase-qx.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07o.md) · **Assignee:** `sase-qx.1` · **Size:** medium
**Created:** 2026-08-19 09:58:31 EDT · **Closed:** 2026-08-19 10:21:36 EDT
**Plan:** [202608/soft\_provider\_disables.md](https://github.com/sase-org/sase--plans/blob/main/202608/soft_provider_disables.md)

## Description

core-mode: add the hard/soft `mode` field to the sase-core provider-disable record, bump the wire schema to 2 with a v1 migration that keeps in-flight disables as hard, and thread the mode through the set/try-set bindings.

## Notes

[2026-08-19T14:21:36Z · sase-qx.1] sase-core just check green. Wire schema is 2; v1 files migrate in place to hard (created_at/expires_at/source preserved) and expired v1 records prune during migration. Unknown v2 mode strings prune without deleting valid siblings; version 3 still deletes the file. All four set/try-set bindings accept hard/soft, default to hard, and raise ValueError on an unknown mode without writing. Landed as sase-core 6169e0e (feat(provider_disable): add hard/soft mode to the disable wire) on origin/master. No --epic-symbol leftovers; sase repo unchanged.

## Dependencies

- **Blocks:** [sase-qx.2](sase-qx.2.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qx.1/README.md) | [sase-qx.1](sase-qx.1.md) | 0 |
