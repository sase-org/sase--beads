# Bead: sase-zw.8.7.2 — Refuse proc cleanup when durable protection coverage is incomplete

[Bead Pages](../README.md) / [sase-zw.8.7](sase-zw.8.7.md) / sase-zw.8.7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.8.land.md) · **Assignee:** `sase-zw.8.7.2` · **Size:** medium
**Created:** 2026-09-14 16:48:12 EDT · **Closed:** 2026-09-15 09:24:06 EDT
**Plan:** [202609/disk\_retention\_final\_safety.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_retention_final_safety.md)

## Description

procs: reject missing or malformed proc stores, preserve unreadable trees, and bound scanning while retaining reservation synchronization.

## Notes

[2026-09-15T13:24:06Z · sase-zw.8.7.2] Implemented proc runtime retention fail-closed coverage in linked sase-core: missing/malformed/mixed proc stores refuse deletion while valid empty stores sweep; unreadable runtime subtrees report errors and are preserved; root/tree scans and capped lookahead are bounded; deletion revalidates root/path just before remove. Verified cargo test -p sase_core procs::runtime::tests, cargo test -p sase_core_py proc_runtime_retention_binding_requires_trustworthy_store_snapshot, LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check in sase-core, just install in main, focused tools/run_pytest proc retention/disk reap tests, tools/validate_sase_core_rs, git diff --check, and no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-zw.8.7.1](sase-zw.8.7.1.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-zw.8.7.3](sase-zw.8.7.3.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.7.2/README.md) | [sase-zw.8.7.2](sase-zw.8.7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@37d6c5c`](https://github.com/sase-org/sase-core/commit/37d6c5c4916333279796396df2ca1bc16466ebc2) | fix(procs): fail closed on incomplete runtime stores | [sase-zw.8.7.2](sase-zw.8.7.2.md) | 2026-09-15 09:26:10 EDT |
