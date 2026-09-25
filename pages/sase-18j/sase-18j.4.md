# Bead: sase-18j.4 — Opt-in stage continuation with exit-code parity

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.4` · **Size:** medium
**Created:** 2026-09-24 19:07:07 EDT · **Closed:** 2026-09-24 21:25:29 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

## Description

keep-going: add the run_silent continuation protocol (SASE_TOOL_CONTINUE handshake, continued/stopped/recipe_finished records, --finish), the recipe finish line, the executor safety net, and sase tool run -k/-x; opt-in and complete, so no flag.

## Notes

[2026-09-25T01:25:04Z · sase-18j.4] PROPOSED FOLLOW-UP: Repair tools/sase_core_wheel_cache extensionless mypy annotations — clean-base just check failure (also noted by sase-18i.2).

[2026-09-25T01:25:29Z · sase-18j.4] Implemented opt-in run_silent continuation: -k/-x validation, recorded continued/stopped/recipe_finished facts, first-exit parity, --finish recipes, nesting scrubs, monitor refusal, and the executor safety net. Verified just fmt and 140 focused tests passed (1 skipped); sase tool run check reached mypy and reproduced the pre-existing sase_core_wheel_cache annotation failure, recorded in the follow-up note.

## Dependencies

- **Depends on:** [sase-18j.1](sase-18j.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18j.6](sase-18j.6.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18j.4/README.md) | [sase-18j.4](sase-18j.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eb64073`](https://github.com/sase-org/sase/commit/eb640735540d73d728e31ecfb1323fe09ba84dd4) | feat(tool): add opt-in stage continuation | [sase-18j.4](sase-18j.4.md) | 2026-09-24 21:27:04 EDT |
