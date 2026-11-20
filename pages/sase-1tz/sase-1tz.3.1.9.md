# Bead: sase-1tz.3.1.9 — Compact oversize provider root bundles at compile time until they fit

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.9` · **Size:** medium
**Created:** 2026-11-20 09:19:07 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

bundle_trim: when a provider declares max_bytes and the delivered bundle would exceed it, compile applies a deterministic compaction ladder. Step one drops summaries from superseded list-roster entries. Step two compacts whole list rosters, largest first. Bundles that already fit stay byte-identical, and no memory file changes.

## Dependencies

- **Blocks:** [sase-1tz.3.1.10](sase-1tz.3.1.10.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.9/README.md) | [sase-1tz.3.1.9](sase-1tz.3.1.9.md) | 0 |
