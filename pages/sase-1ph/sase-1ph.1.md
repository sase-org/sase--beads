# Bead: sase-1ph.1 — Restore the lost sase-core ToolRun contention and quarantine fix (sase-1p6)

[Bead Pages](../README.md) / [sase-1ph](README.md) / sase-1ph.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5f.final.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5f.final.f0.md) · **Assignee:** `sase-1ph.1` · **Size:** small
**Created:** 2026-10-28 20:02:59 EDT · **Closed:** 2026-10-28 20:31:06 EDT
**Plan:** [202610/recover\_handoff\_lost\_edits.md](https://github.com/sase-org/sase--plans/blob/main/202610/recover_handoff_lost_edits.md)

## Description

core-contention: apply the replayed sase-1ou.land patch to sase-core (contention.rs test budgets plus the connection.rs open/quarantine fix), verify it with the governed sase-core check, and close sase-1p6 with fresh evidence.

## Notes

[2026-10-29T00:31:06Z · sase-1ph.1] Applied the replayed sase-1ou.land patch to sase-core (connection.rs + contention.rs test budgets/quarantine fix, base ed8328f9). Verified: the two new regression tests fail with connection.rs reverted and pass with it restored; all 14 contention tests and 142 tool_run::store lib tests pass; governed sase-core sase tool run check passed (run 7263dbbc242092b063064170622d32d7, exit 0). core_stress=reuse so no stress rerun. Closed sase-1p6 with fresh evidence. No epic-symbol leftovers. sase-core-revision.txt pin untouched.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ph.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ph.1/README.md) | [sase-1ph.1](sase-1ph.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@df14e8f`](https://github.com/sase-org/sase-core/commit/df14e8f4386bc64f6614ad48cf0de19026a8cd18) | fix(tool\_run): owe every call one store open and recreate after quarantine | [sase-1ph.1](sase-1ph.1.md) | 2026-10-28 20:32:43 EDT |
