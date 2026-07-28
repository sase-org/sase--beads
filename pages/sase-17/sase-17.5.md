# Bead: sase-17.5 — Phase 2E: Move Hot Call Sites to Batch Query Evaluation

[Bead Pages](../README.md) / [sase-17](README.md) / sase-17.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-17.5`
**Created:** 2026-04-29 06:53:45 UTC · **Closed:** 2026-04-29 07:54:00 UTC
**Plan:** [202604/rust\_backend\_phase2\_query.md](https://github.com/sase-org/sase--plans/blob/main/202604/rust_backend_phase2_query.md)

## Description

Make Phase 2 measurable in user-facing paths by avoiding per-row FFI dispatch. Update high-volume call sites to use the batch facade: src/sase/ace/tui/actions/changespec/_loading.py, src/sase/axe/cli.py, src/sase/main/search_handler.py, and src/sase/axe/check_cycles.py if it can use the same shape without weakening behavior. Add tests proving batch results match evaluate_query_with_context for representative lists including ancestor and sibling filters. Keep syntax highlighting in Python this phase.

## Notes

COMMIT: eb8ed7ee

## Dependencies

- **Depends on:** [sase-17.4](sase-17.4.md) ✓
- **Blocks:** [sase-17.6](sase-17.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`41ae7f7`](https://github.com/sase-org/sase/commit/41ae7f73d3ab6363633c25da53c43aba585aec1b) | feat(core): Phase 2E — route hot query call sites through evaluate\_query\_many (sase-17.5) | [sase-17.5](sase-17.5.md) | 2026-04-29 07:54:04 |
