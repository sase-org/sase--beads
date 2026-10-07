# Bead: sase-1hf.1 — Race-free ready.json publication and reading

[Bead Pages](../README.md) / [sase-1hf](README.md) / sase-1hf.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y0.md) · **Assignee:** `sase-1hf.1` · **Size:** small
**Created:** 2026-10-07 14:45:43 EDT · **Closed:** 2026-10-07 15:23:18 EDT
**Plan:** [202610/wait\_lane\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_lane_repair.md)

## Description

atomic-ready: publish ready.json via temp file plus no-clobber link, skip publishing once the waiter is gone, and make the runner treat unreadable or malformed ready.json as not ready.

## Notes

[2026-10-07T19:22:52Z · sase-1hf.1] PROPOSED FOLLOW-UP: just check red on clean base too — SASE validation init repo --check wants sase/repos/beads/README.md refresh (+4/-4 sidecar drift) and symvision flags _runs imports in agents_sync/v2_snapshot_io.py and decks/final/overview_card.py (KNOWN with witness); all outside this phase diff

[2026-10-07T19:23:18Z · sase-1hf.1] atomic-ready done: publish_ready_marker (temp+fsync+no-clobber link, skips when waiting.json gone) wired into wait_checks with lost-race counted as already_ready; read_ready_result returns False on torn/empty/non-dict markers, legacy cancelled handling kept; TUI writer untouched; docs/axe.md updated. Verified: 9 new tests in tests/test_atomic_ready_marker.py pass, 49 neighboring wait-deps/chop tests pass, fmt/ruff/mypy gates pass; remaining check reds (init repo sidecar drift, 2 KNOWN symvision) reproduce on clean base and are recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1hf.3](sase-1hf.3.md) ◐ · ⧖ 2026-10-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1hf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1hf.1/README.md) | [sase-1hf.1](sase-1hf.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4cbfe00`](https://github.com/sase-org/sase/commit/4cbfe00d979c956a52e93a5f188da1037316107c) | fix(axe): atomically publish agent wait ready markers | [sase-1hf.1](sase-1hf.1.md) | 2026-10-07 15:38:17 EDT |
