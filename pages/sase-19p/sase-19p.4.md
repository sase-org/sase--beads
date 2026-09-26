# Bead: sase-19p.4 — Clear the agent-session terminology regression in closed-bead landing

[Bead Pages](../README.md) / [sase-19p](README.md) / sase-19p.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19p.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19p.land.md) · **Assignee:** `sase-19p.4.land`
**Created:** 2026-09-25 21:50:31 EDT · **Closed:** 2026-09-26 06:59:29 EDT
**Plan:** [202609/agent\_closed\_bead\_landing\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_closed_bead_landing_cleanup.md)

## Description

The close-attribution epic passes its terminology contract on the integrated tree, with no remaining failures caused by sase-19p.

## Notes

[2026-09-26T10:59:29Z · sase-19p.4.land] Verified sase-19p.4.1 against the integrated tree. The capacity projection docstring in src/sase/core/runner_slots/_admission_capacity_records.py (capacity_session_keys_for_core) documents the legacy parallel marker without naming agent_family_parallel; that wording landed in 22e5414a9. Phase stitch fffdaeb3e8 curated tests/test_agent_session_terminology.py into tests/contract_manifest.txt (budget 69) and set queue_capacity_multiplier=None on the two wait-queue AgentInfo fixtures. Re-ran tests/test_agent_session_terminology.py, tests/core/test_bead_touch_index_facade.py, tests/test_bead/test_cli_close_note.py, tests/test_bead/test_cli_touched.py, and tests/ace/tui/widgets/test_agent_bead_touch_rows.py: 74 passed. No agent_family identifiers remain outside the terminology allowlist. Commits after fffdaeb3e8 do not touch those files, do not add AgentInfo fields, and do not reintroduce the retired identifier (terminology guard still green). No --epic-symbol entries for this epic.

Follow-ups declined, both already fixed on master: sase-19p.4.1#1 ruff F601 duplicate node_finder_preview_loader _source_paths key was present at 4ee966cd56 (lines 242 and 266) and removed by 465a8858b9; the audit dict now has one key. sase-19p.4.1#2 four stale --epic-symbol entries for closed sase-1aa.3 were re-keyed to open sase-1aa.4 by e2b462548c. Neither was filed.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19p.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19p.4.land/README.md) | [sase-19p.4](sase-19p.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@c141c1d`](https://github.com/sase-org/sase--plans/commit/c141c1d35680e45d7c3eb6817f8a2c6c26efd0cc) | chore(plan): mark agent-closed bead landing plans done | [sase-19p.4](sase-19p.4.md) | 2026-09-26 07:12:02 EDT |
