# Bead: sase-1cp.4 — sase tool run refuses inline runs that cannot fit

[Bead Pages](../README.md) / [sase-1cp](README.md) / sase-1cp.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u2.md) · **Assignee:** `sase-1cp.4` · **Size:** medium
**Created:** 2026-09-29 16:48:03 EDT · **Closed:** 2026-09-29 18:18:34 EDT
**Plan:** [202609/tool\_inline\_routing.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_inline_routing.md)

## Description

ceiling-refusal: before any reconcile, reservation, or spawn, refuse an agent's inline named-tool run whose class floor meets the exported ceiling (exit 2), print the monitor and prepared-completion forms, and update tests, docs, and the sase_monitor skill source.

## Notes

[2026-09-29T22:18:04Z · sase-1cp.4] PROPOSED FOLLOW-UP: just check fails on pre-existing _lint-patch-stitch-terminology defects in sase-core linked-repo fixture at_bearing_notes.jsonl (14 defect lines); reproduces identically (exit 1) on the clean base tree with this phase stashed, so unrelated to ceiling-refusal work

[2026-09-29T22:18:34Z · sase-1cp.4] ceiling-refusal landed: new src/sase/tool/routing.py (read_sync_ceiling, inline_refusal, shared monitor_start_form; handoff_launch refactored byte-identical, pinned by existing handoff tests); execute_tool_run refuses agent inline long/unbounded runs at/over the ceiling with exit 2 before reconcile/reservation/spawn, printing monitor + prepared-completion forms. Verified: 15 new tests/tool/test_routing.py pass; tests/tool+tool_handler+completion 352 passed 1 skipped; ruff+mypy clean; just fix clean; completion snapshot no drift; epic-symbols none. Full just check blocked only by pre-existing sase-core fixture terminology-lint failure reproduced identically on clean base (recorded as PROPOSED FOLLOW-UP). check stays short by design; no digests moved.

## Dependencies

- **Depends on:** [sase-1cp.2](sase-1cp.2.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cp.3](sase-1cp.3.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cp.4/README.md) | [sase-1cp.4](sase-1cp.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b07172c`](https://github.com/sase-org/sase/commit/b07172cc1d8b73105a4f4ae140471e538e2e5a24) | feat(tool-run): refuse inline runs that cannot fit the provider ceiling | [sase-1cp.4](sase-1cp.4.md) | 2026-09-29 18:20:28 EDT |
