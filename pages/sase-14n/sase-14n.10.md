# Bead: sase-14n.10 — Reclaim quarantined ToolRun stores

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.10` · **Size:** medium
**Created:** 2026-09-20 17:14:18 EDT · **Closed:** 2026-09-20 19:10:28 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

toolrun_retention: extend sase-core's tool_run retention selection to quarantined corrupt stores and surface them through the existing preview and apply reports.

## Notes

[2026-09-20T23:10:28Z · sase-14n.10] Quarantined ToolRun stores reclaimed at the log_days horizon. sase-core retention scans runs.sqlite.corrupt-* siblings (main plus -wal/-shm sidecars), selects those older than log_days by filename quarantine nanos, and surfaces them as kind=quarantined_store through the existing preview/apply report; Rust never deletes files, the thin tool_run_retention reaper does. Young/unreadable quarantine bytes stay in retained_bytes with over_target recomputed, and orphan quarantines are previewed without a live store. No wire/config/schema change, so no sase-core release or floor raise is needed. Verified: cargo test -p sase_core --lib tool_run:: 30 passed (2 new beside quarantine/retention cases), clippy clean; pytest tests/tool/test_retention_files.py 3 passed (new preview+reclaim test); recorded sase tool run check: all lint gates passed, 44230 tests passed, only 2 failures in test_capacity_gate_to_admission.py which are the still-open sase-13o defect (fix 19c515e0a not in this workspace) with zero references to retention. Diffs: sase tests/tool/test_retention_files.py +60; sase-core crates/sase_core/src/tool_run/store.rs +231/-14.

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14n.10/README.md) | [sase-14n.10](sase-14n.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2b68fc9`](https://github.com/sase-org/sase/commit/2b68fc9b3886460bf6020d40172e0f783eea03b5) | test(tool): cover quarantined ToolRun store reclaim at log horizon | [sase-14n.10](sase-14n.10.md) | 2026-09-20 19:12:42 EDT |
