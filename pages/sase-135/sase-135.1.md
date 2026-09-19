# Bead: sase-135.1 — Establish the versioned ToolRun store and bindings

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.1` · **Size:** medium
**Created:** 2026-09-18 22:19:18 EDT · **Closed:** 2026-09-19 03:04:16 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

## Description

core-ledger: Implement section 1, including Rust records, event/projection transactions, reconciliation and retention policy, golden fixtures, PyO3 bindings, the initial disk owner, and a forward-only core pin update.

## Notes

[2026-09-19T07:03:35Z · sase-135.1--4] PROPOSED FOLLOW-UP: bump sase-core-revision.txt after this ToolRun core SHA is on GitHub — phase 1 implemented the V1 store but left the pin at 8d5341a because the local core SHA is unpublished; do not add tool_run_* to published-floor REQUIRED_BINDINGS until a containing sase-core release exists.

[2026-09-19T07:04:16Z · sase-135.1--4] Verified V1 ToolRun store/bindings (catalog+fingerprint contracts; begin/append/finish/reconcile/list/show/summary/retention/stats; goldens); reserved unresolved artifact kind tool (known_kinds updated); disk inventory/reap owner tool_run_retention; smokes + pytest twins + Justfile smoke-tool-runs. just check green on Justfile-escalated full fast lane (monitor 9sch46dk84vn: Required checks passed, ✓ test (scoped)). Session detach-scope guards preserved so agent-cgroup just check does not leak systemd-run wrapping; doctor systemd-scope matrix delenvs the session disable flag. Core pin not moved (still 8d5341a; unpublished local SHA). published-floor REQUIRED_BINDINGS and release-core-floor-smoke not expanded. epic-symbols empty (later-phase leftovers keyed to sase-135.2/135.3/135.5).

## Dependencies

- **Blocks:** [sase-135.2](sase-135.2.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-135.1.md) | [sase-135.1](sase-135.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9cfa200`](https://github.com/sase-org/sase/commit/9cfa20067519122b6737890dff68a883d43e49d2) | feat(tool-run): land V1 ToolRun bindings, disk owner, and smokes | [sase-135.1](sase-135.1.md) | 2026-09-19 04:46:06 EDT |
