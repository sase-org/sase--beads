# Bead: sase-1nf.2 — Truthful managed\_tmp\_reap and disk\_pressure jobs on the new core

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.2` · **Size:** medium
**Created:** 2026-10-20 13:36:13 EDT · **Closed:** 2026-10-20 15:07:36 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

reap-sase: move the core pin, log removal errors and blocking processes, make managed_tmp_reap report check_error on removal failures, make disk_pressure reap before notifying with an explicit status table, and update the housekeeping and runtime docs.

## Notes

[2026-10-20T19:07:23Z · sase-1nf.2] PROPOSED FOLLOW-UP: Refresh the stale contract-test manifest — just check ToolRun d2ac44070c47ed2dc70f55fe0f63d7e0 failed tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection with stale ordering; sase-1n8.3 note #1 verified the same failure on a clean base, and sase-1fl tracks stale contract manifests. The run also hit the already-tracked parallel Textual flake sase-1gg. Both touched test files passed focused ToolRun 23c5a914440c3cbc083925a2cde40076 (25 passed).

[2026-10-20T19:07:36Z · sase-1nf.2] Implemented truthful managed_tmp_reap and disk_pressure outcomes, moved sase-core-revision.txt to reap-core commit 6f354df4, rebuilt the binding, updated docs/config descriptions, and verified 25 focused tests pass in ToolRun 23c5a914440c3cbc083925a2cde40076. just check's lint, SASE validation, and docs stages passed; the test lane was red only on the clean-base stale contract manifest and known sase-1gg flake, recorded as a proposed follow-up. epic-symbols confirmed no leftovers.

## Dependencies

- **Depends on:** [sase-1nf.1](sase-1nf.1.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.2/README.md) | [sase-1nf.2](sase-1nf.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4136946`](https://github.com/sase-org/sase/commit/413694618eb7ee102ce8f5b785575c605353ee98) | fix(cleanup): report managed tmp and disk pressure outcomes | [sase-1nf.2](sase-1nf.2.md) | 2026-10-20 15:09:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.2/README.md

<!-- sase:referenced-by:end -->
