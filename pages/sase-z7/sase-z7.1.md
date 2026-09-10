# Bead: sase-z7.1 — Define shared usage window identity and visibility policy

[Bead Pages](../README.md) / [sase-z7](README.md) / sase-z7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hy.md) · **Assignee:** `sase-z7.1` · **Size:** medium
**Created:** 2026-09-10 07:06:07 EDT · **Closed:** 2026-09-10 07:50:56 EDT
**Plan:** [202609/usage\_window\_indicators.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_indicators.md)

## Description

window-policy: implement Rust classification, policy validation and selection, time-aware projection, bindings, and contract tests.

## Notes

[2026-09-10T11:50:56Z · sase-z7.1] Implemented shared provider-usage indicator policy/projection API and PyO3 bindings in sase-core. Verified cargo test -p sase_core provider_usage::tests::indicator, cargo test -p sase_core_py provider_usage_bindings, cargo test -p sase_core_py --lib with Python 3.12 runtime, and full isolated core just check with PYO3_PYTHON=/home/bryan/.local/bin/python3.12 LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib CARGO_TARGET_DIR=target/sase-z7-check. Ran sase bead epic-symbols sase-z7.1: no entries.

## Dependencies

- **Blocks:** [sase-z7.2](sase-z7.2.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-z7.3](sase-z7.3.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z7.1/README.md) | [sase-z7.1](sase-z7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7c949b4`](https://github.com/sase-org/sase-core/commit/7c949b46c3ae656a84b5a94759ddcb926fa6f3c1) | feat: add usage indicator policy projection | [sase-z7.1](sase-z7.1.md) | 2026-09-10 07:52:17 EDT |
