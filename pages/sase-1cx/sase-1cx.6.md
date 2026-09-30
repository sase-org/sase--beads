# Bead: sase-1cx.6 — Agent sase tool run escalates instead of being killed

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.6` · **Size:** large
**Created:** 2026-09-29 20:32:20 EDT · **Closed:** 2026-09-30 13:24:09 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

inline-escalation: when the flag is on and a budget exists, an agent's plain `sase tool run` starts detached and follows the run with inline-identical output. On settlement it returns the run's exit. At the budget or on a signal it prints the escalation block and exits without stopping the run. It falls back to today's inline run whenever detaching is unavailable.

## Notes

[2026-09-30T16:52:35Z · sase-1cx.6] inline-escalation environment parity (re-read 2026-09-30): guarded recipes unchanged — tools/require_tool_run allows when SASE_AGENT is unset, only check and check-full carry the _require-tool-run guard (Justfile), inline passes on SASE_TOOL_NAME+root, detached passes because _supervisor_env (src/sase/procs/spawn.py) scrubs SASE_AGENT* plus both ceilings and pops SASE_ARTIFACTS_DIR, and check does not invoke check-full. check-full is the one catalog difference and only when this path runs it: default_is_ci (tests/ace/tui/visual/_visual_maintenance_guards.py) treats workspace CI=true as real CI unless SASE_AGENT or SASE_MONITOR_ID is set; the detached child has neither so a golden update inside check-full is refused where the inline child would be allowed; GITHUB_ACTIONS refuses either way; check-full is duration_class long so a 600s hard ceiling still refuses it before this path via inline_refusal; check, install, test do not update goldens. SASE_AGENT is not re-injected into the child and default_is_ci is unchanged. Stdin not inherited on the automatic path (supervisor stdin=DEVNULL) vs inherited inline (spawn_child stdin=None) is intentional and documented in help + docs/tool.md, not a follow-up. PROPOSED FOLLOW-UP: detached check-full under workspace CI=true refuses golden updates after the proc scrub drops SASE_AGENT — default_is_ci has no tool-run marker, and re-injecting SASE_AGENT would undo the scrub.

[2026-09-30T17:24:09Z · sase-1cx.6] inline-escalation implemented and verified: 18/18 tests/tool/test_inline_escalation.py pass (fast settle parity, -v streaming, 124 escalation + later wait exit, SIGTERM 143 with run live, -k/-x/known envelope modes, starter/submit fail-open fallbacks, all five stay-inline gates, long refusal first, exit mapping + ledger footer renderer units); harness dod-17-inline-escalation passes (follower 124, wait 3, one row); regressions green (executor, detach, handoff, bounded_wait, routing); ruff+mypy+flags+pyscripts+waits+changelog+terms+prettier clean. Environment parity recorded earlier on this bead (guarded-recipe + scrub behavior confirmed, check-full golden-update gap filed as PROPOSED FOLLOW-UP). Automatic-path stdin documented in help + docs/tool.md (inherited inline incl. fallback, DEVNULL detached). sase tool run check itself is blocked by a pre-existing environment failure (validate_sase_core_rs prompt-prediction probe confident=False fails identically on the untouched base; symvision baseline likewise identical).

## Dependencies

- **Depends on:** [sase-1cx.2](sase-1cx.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.3](sase-1cx.3.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.4](sase-1cx.4.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1cx.7](sase-1cx.7.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cx.6.md) | [sase-1cx.6](sase-1cx.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c68da8c`](https://github.com/sase-org/sase/commit/c68da8c475e6fb00403827e0a4926970bc0a1918) | feat(tool): add inline escalation to detached handoff run | [sase-1cx.6](sase-1cx.6.md) | 2026-09-30 13:28:02 EDT |
