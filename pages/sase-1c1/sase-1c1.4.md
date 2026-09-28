# Bead: sase-1c1.4 — Repair whole-repo contract and guard drift

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.4` · **Size:** medium
**Created:** 2026-09-28 07:09:28 EDT · **Closed:** 2026-09-28 09:49:09 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

contract-drift: fix the 15 mechanical failures. Add completion kinds and sync the spec, add the two schema properties, fix the AgentExecContext mock, and update the trash-limit and getting-started docs assertions. Review the two marker-path sites, and route the 7 system-clock sites through sase.core.time without touching the allowlist.

## Notes

[2026-09-28T13:48:23Z · sase-1c1.4--1] PROPOSED FOLLOW-UP: just check on this change-set escalates to the full suite (src-data-asset from sase.schema.json plus core-identity-changed from the linked sase-core checkout) and the 1h verify monitor timed out after lint/fmt/validate passed — remaining full-suite redness belongs to sibling phases, sase-1c1.13, and sase-18s

[2026-09-28T13:49:09Z · sase-1c1.4--1] Verified the 15 mapped contract-drift failures: completion kinds+snapshot, public schema (tools.receipt and ace.keymaps.tool_runs), AgentExecContext.agent_meta mock, trash-limit constant, getting-started wording, reviewed marker-path sites finalizers/cli.py:_target_for_dir and axe/run_agent_directive_metadata.py:session_root_tab, and routed the 7 system-clock sites through sase.core.time without extending the allowlist. 185 targeted tests passed including timezone guard, marker-path audit, schema, completion, mock skew, trash limit, getting-started, and clock-display assertions. Fixes sase-18s completion nodes, sase-1bp, sase-1by, sase-1bq, sase-1as, and sase-1bc note #3. just check lint/fmt/validate passed; test-scoped escalated to the full suite and the 1h monitor timed out (see note #1).

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.4.md) | [sase-1c1.4](sase-1c1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ef77145`](https://github.com/sase-org/sase/commit/ef7714508aed1642dba65fb84c3ba37d6456068f) | fix(ci): repair whole-repo contract and guard drift (sase-1c1.4) | [sase-1c1.4](sase-1c1.4.md) | 2026-09-28 09:51:18 EDT |
