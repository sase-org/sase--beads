# Bead: sase-n8.7 — PNG goldens for the history panel

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.7` · **Size:** medium
**Created:** 2026-08-16 11:33:01 EDT · **Closed:** 2026-08-16 15:57:58 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

visual: add deterministic fixtures and PNG snapshot coverage for the history panel's populated, grouped, truncated, legacy-provenance, and empty states, and confirm no existing Launch Control golden moves.

## Notes

[2026-08-16T19:55:47Z · sase-n8.7] PROPOSED FOLLOW-UP: Clean stale Symvision epic allowlist entries — just check fails before scoped tests because closed bead sase-n9 is still listed for agent_family_plan_preview_detail/documentation/cache_key.

[2026-08-16T19:56:45Z · sase-n8.7] PROPOSED FOLLOW-UP: Rebaseline or fix stale Launch Control visual goldens — existing model-panel PNG suite still fails 40/43 without updating; H footer leakage was removed, but remaining diffs predate this visual phase and include backdrop/provider drift.

[2026-08-16T19:57:58Z · sase-n8.7] Added deterministic alias-history visual fixtures/tests and five PNG goldens for populated, grouped, truncated, legacy-only, and empty states. Verified new module update and no-update runs pass, plus alias-history targeted suite 74 passed. just check is blocked before scoped tests by unrelated stale Symvision sase-n9 allowlist entries; existing Launch Control visual suite still has stale baseline failures recorded as proposed follow-ups.

[2026-08-16T20:00:05Z · sase-n8.7] Verified alias-history PNG snapshots with uv run pytest tests/ace/tui/visual/test_ace_png_snapshots_models_panel_alias_history.py -m visual and targeted alias-history suite; ran just check, blocked by unrelated stale Symvision allowlist for closed bead sase-n9; recorded proposed follow-ups for that and stale existing Launch Control PNG baselines.

## Dependencies

- **Depends on:** [sase-n8.6](sase-n8.6.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n8.8](sase-n8.8.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.7/README.md) | [sase-n8.7](sase-n8.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bbc24e4`](https://github.com/sase-org/sase/commit/bbc24e472e53ffb067c4cc41137f5885f70775c3) | fix(ace): keep Launch Control footer stable | [sase-n8.7](sase-n8.7.md) | 2026-08-16 16:01:49 EDT |
