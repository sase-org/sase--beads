# Bead: sase-z4.1 — Define weighted queue contracts and shared capacity policy in Rust

[Bead Pages](../README.md) / [sase-z4](README.md) / sase-z4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i5.md) · **Assignee:** `sase-z4.1` · **Size:** medium
**Created:** 2026-09-09 20:51:14 EDT · **Closed:** 2026-09-09 21:33:15 EDT
**Plan:** [202609/weighted\_queue\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_queue_capacity.md)

## Description

core-contracts: implement the validated weight value, queue and launch wire changes, deterministic capacity projection and admission policy, editor metadata, and PyO3 contracts.

## Notes

[2026-09-10T01:33:15Z · sase-z4.1] Implemented Rust queue weight parsing/formatting, launch/scan/editor/PyO3 wire support, and shared runner capacity snapshot policy; verified with cargo test -p sase_core --lib, cargo test -p sase_core_py directive_contract_and_completion_bindings_return_plain_json_shapes --lib, focused LSP queue tests, and LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check.

## Dependencies

- **Blocks:** [sase-z4.2](sase-z4.2.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.1/README.md) | [sase-z4.1](sase-z4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@63bb275`](https://github.com/sase-org/sase-core/commit/63bb275ef9563903b8d8c02b666997cfe1312c87) | feat(core): add weighted queue capacity contracts | [sase-z4.1](sase-z4.1.md) | 2026-09-09 21:34:32 EDT |
