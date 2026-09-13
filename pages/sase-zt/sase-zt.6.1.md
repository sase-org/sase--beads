# Bead: sase-zt.6.1 — Complete canonical capacity records and editor semantics in Rust

[Bead Pages](../README.md) / [sase-zt.6](sase-zt.6.md) / sase-zt.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.land.md) · **Assignee:** `sase-zt.6.1` · **Size:** medium
**Created:** 2026-09-13 07:09:18 EDT · **Closed:** 2026-09-13 08:13:59 EDT
**Plan:** [202609/queue\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_landing_repairs.md)

## Description

core-contracts: preserve canonical and legacy capacity through metadata, waiting markers, launch wires and indexed scans; share persisted-zero handling and flag-aware editor suggestions in Rust.

## Notes

[2026-09-13T12:12:41Z · sase-zt.6.1] Verified on sase-core parent a64c40dfc3719eefcbadb6a5869adb28f0158806. Advanced AGENT_SCAN_WIRE_SCHEMA_VERSION 8→9 and AGENT_ARTIFACT_INDEX_SCHEMA_VERSION 28→29. Scan/index/launch/admission read canonical queue_capacity, legacy wait_runners, and dual-written records (canonical wins); writers emit canonical names. Persisted explicit zero is shared as exact effective-weight drain via normalize_persisted_queue_capacity (reauthor_capacity omitted so continuations do not re-parse authored zero). Queue editor/LSP suggestions are flag-aware: On offers 1/100 PositiveInt budget help, Off keeps 0 drain. PYO3_PYTHON=/usr/bin/python3: cargo fmt --check, clippy -D warnings, sase_core 2644 tests, sase_core_py 144 tests, sase_xprompt_lsp tests passed. just check failed only on pre-existing sase_gateway routes::tests::fleet_mutate_refuses_terminal_missing_capability_and_bridge_failure (empty catalog).

[2026-09-13T12:13:17Z · sase-zt.6.1] PROPOSED FOLLOW-UP: sase_gateway routes::tests::fleet_mutate_refuses_terminal_missing_capability_and_bridge_failure panics at first_summary ("seeded fleet row") in isolation on this host — did not touch gateway; other fleet_reads seed tests passed; unrelated to queue capacity.

[2026-09-13T12:13:59Z · sase-zt.6.1] Canonical queue_capacity is preserved through Rust metadata, waiting markers, launch wires, and index schema 29; dual/legacy aliases deserialize without duplicate-field errors; persisted explicit zero is an exact effective-weight drain; On editor/LSP suggestions are 1/100 not 0. Verified with PYO3_PYTHON=/usr/bin/python3: fmt, clippy -D warnings, sase_core 2644 tests, sase_core_py 144 tests, sase_xprompt_lsp tests. Parent SHA a64c40d. just check also hit pre-existing sase_gateway fleet_mutate seeded-row failure (untouched).

## Dependencies

- **Blocks:** [sase-zt.6.2](sase-zt.6.2.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.6.1/README.md) | [sase-zt.6.1](sase-zt.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa84150`](https://github.com/sase-org/sase/commit/fa84150cd9ef52097aacbd3b276db9ba023b58d4) | feat(ace): honor queue\_capacity\_budget in LSP and editor contract | [sase-zt.6.1](sase-zt.6.1.md) | 2026-09-13 08:15:53 EDT |
