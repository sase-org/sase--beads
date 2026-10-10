# Bead: sase-1j6.1 — Exec-first runner refresh and import firewall

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.1` · **Size:** small
**Created:** 2026-10-09 15:02:04 EDT · **Closed:** 2026-10-09 15:17:23 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

refresh-exec-first: remove every lazy sase import between the HEAD-moved check and os.execv in refresh_runner_code_after_wait, move the %auto reconcile into the refreshed process, and add an import-firewall test.

## Notes

[2026-10-09T19:16:53Z · sase-1j6.1] PROPOSED FOLLOW-UP: stale sase_core_rs wheel in this workspace lacks autonomy_record_from_legacy_meta / autonomy_resolve_selection, failing 5 base tests (4 reconcile cases in test_plan_auto_live_meta.py, test_refresh_local_macros_boundary_replay); rerun after just install-venv rebuilds the wheel

[2026-10-09T19:17:07Z · sase-1j6.1] PROPOSED FOLLOW-UP: skipped decisions-web record for update-skew at-most-once pre-provider-only restarts, per epic auto decision decision_record=no

[2026-10-09T19:17:23Z · sase-1j6.1] Exec-first refresh done: zero sase.* imports between identity check and execv (hoisted multi_prompt_macros helpers + directive-identity check, warmed sase.core.paths/sase.agent.names leaves), %auto reconcile moved to refreshed-pass bootstrap before directive extraction; verified by new import-firewall test, 4 refreshed-pass toggle cases + non-refreshed gate test, ruff+mypy clean; 2 serialize patch-targets retargeted to refresh namespace; 5 remaining failures reproduce identically on clean base (stale sase_core_rs wheel) and are logged as PROPOSED FOLLOW-UP

## Dependencies

- **Blocks:** [sase-1j6.9](sase-1j6.9.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.1/README.md) | [sase-1j6.1](sase-1j6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6ac3dc7`](https://github.com/sase-org/sase/commit/6ac3dc734e23f597502d011c4b6580ec7720a1fe) | fix(axe): keep runner code refresh import-free before re-exec | [sase-1j6.1](sase-1j6.1.md) | 2026-10-09 15:19:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.2][1] | Check sibling phase to avoid conflicting edits | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.2/README.md

<!-- sase:referenced-by:end -->
