# Bead: sase-1pn.2 — Stop a preservation refusal from poisoning its workspace slot (sase-1p9)

[Bead Pages](../README.md) / [sase-1pn](README.md) / sase-1pn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.land.md) · **Assignee:** `sase-1pn.2` · **Size:** medium
**Created:** 2026-10-29 10:44:08 EDT · **Closed:** 2026-10-29 13:19:37 EDT
**Plan:** [202610/task\_backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_2.md)

## Description

slot-refusal: remember launch-time nested-preservation refusals per workspace, apply the slot_refusal decision, and raise one actionable notification instead of failing every later launch there.

## Notes

[2026-10-29T17:19:15Z · sase-1pn.2] TASK RESOLVED: sase-1p9 — nested-preservation refusal now records a durable per-slot quarantine; claim_next forwards skip_workspaces so the Rust allocator skips the slot; pinned spawn fails fast with the repair command; one notification per standing record; auto-clear when the nested repo is clean/gone or later preserve succeeds; force-clear via sase workspace repair -C

[2026-10-29T17:19:23Z · sase-1pn.2] PROPOSED FOLLOW-UP: test_start_monitor_scrubs_agent_identity_from_the_supervisor_env fails on clean base (sase-1pg) — SASE_AGENT remains in supervisor env

[2026-10-29T17:19:28Z · sase-1pn.2] PROPOSED FOLLOW-UP: sase-core just check flake: sudo_runner::tests::dispatch::permission_denied_cwd_fails_before_dispatch_when_supported panics EOF-parsing JSON under parallel load; passes alone on clean HEAD

[2026-10-29T17:19:37Z · sase-1pn.2] Verified slot_refusal=quarantine: dirty nested preserve records one refusal and notification; auto-allocate skips the slot (Rust skip_workspaces + Python get_first_available_workspace); pinned spawn fails fast with sase workspace repair -C; successful preserve and --clear-refusal clear the record. sase lint (mypy/ruff/symvision) passed; 59 targeted Python tests passed; allocate_and_claim_skips_quarantined_workspaces passed. just check NEW/FLAKY/KNOWN leftovers are clean-base (sase-1pg) or unrelated sudo_runner load flake. No leftover --epic-symbol rows.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pn.2/README.md) | [sase-1pn.2](sase-1pn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1762b33`](https://github.com/sase-org/sase-core/commit/1762b33a12a9d91841162dde52db5d9e4d429916) | fix(workspace): skip quarantined slots in allocate\_and\_claim | [sase-1pn.2](sase-1pn.2.md) | 2026-10-29 13:20:57 EDT |
