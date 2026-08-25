# Bead: sase-tt.7 — Take the external-issue network call off the Bead first-paint path

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.7` · **Size:** medium
**Created:** 2026-08-25 14:59:16 EDT · **Closed:** 2026-08-25 16:21:50 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

beads: move the in-band `gh` subprocess out of the Bead snapshot worker into a background refresh, and remove the repeated project-alias and external-ref work in the same load.

## Notes

[2026-08-25T20:21:06Z · sase-tt.7] PROPOSED FOLLOW-UP: Refresh generated memory shims - `just check` currently fails SASE validation because `sase init memory --check` wants AGENTS/provider shims regenerated; this is unrelated to the Bead first-paint change.

[2026-08-25T20:21:50Z · sase-tt.7] Verified: .venv/bin/python -m pytest tests/ace/tui/test_artifacts_beads_loading.py; .venv/bin/python -m pytest tests/ace/tui/test_artifacts_beads_rendering.py tests/ace/tui/test_artifacts_beads_filtering.py; .venv/bin/python -m pytest -q -m slow tests/perf/bench_artifacts_first_paint.py; .venv/bin/python -m pytest tests/test_bug_links.py tests/ace/tui/test_artifacts_beads_loading.py; just _lint-symvision. just check reached SASE validation and failed only because init memory --check wants generated AGENTS/provider shims refreshed; recorded PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.7/README.md) | [sase-tt.7](sase-tt.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e234d5d`](https://github.com/sase-org/sase/commit/e234d5df9bd3422c6fa099bbd727ee90f54dac1a) | perf(beads): defer external issue refresh | [sase-tt.7](sase-tt.7.md) | 2026-08-25 16:23:47 EDT |
