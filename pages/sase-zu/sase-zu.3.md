# Bead: sase-zu.3 — Artifact index gains full-history candidate filtering and machine provenance

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.05.f0` · **Assignee:** `sase-zu.3` · **Size:** medium
**Created:** 2026-09-12 10:35:45 EDT · **Closed:** 2026-09-12 16:45:26 EDT
**Plan:** [202609/agent\_query\_load\_tiering.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_load_tiering.md)

## Description

rust_index: in sase-core, apply the candidate filter on the non-windowed selection path, add an indexed machine-provenance column, and bump the artifact index schema version.

## Notes

[2026-09-12T20:45:26Z · sase-zu.3] Implemented schema-28 Rust artifact index full-history candidate filtering and source-machine projection; verified cargo fmt --check, Rust targeted tests, agent_scan_parity, python_wire_parity, Python wire/oracle/gh tests, epic-symbols empty, and just check.

## Dependencies

- **Depends on:** [sase-zu.1](sase-zu.1.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.4](sase-zu.4.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.5](sase-zu.5.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.3/README.md) | [sase-zu.3](sase-zu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c1185c`](https://github.com/sase-org/sase/commit/3c1185c2819b3e693b1686b64348daaef2cdc013) | feat(agent-scan): mirror schema 28 index filtering | [sase-zu.3](sase-zu.3.md) | 2026-09-12 16:47:37 EDT |
