# Bead: sase-v.3 — Phase 3 — TUI integration, modal, help modal, error surfacing

[Bead Pages](../README.md) / [sase-v](README.md) / sase-v.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-v.3`
**Created:** 2026-04-26 07:31:09 UTC · **Closed:** 2026-04-26 08:15:21 UTC
**Plan:** [202604/agents\_tab\_query\_filters.md](https://github.com/sase-org/sase--plans/blob/main/202604/agents_tab_query_filters.md)

## Description

User-visible. Replace inline _matches() in _finalize_agent_list() with parse_agent_query() + evaluate_agent_query(); cache parsed AST keyed by raw query string. Preserve hierarchy logic. Surface AgentQueryParseError as transient toast with no-filter fallback. Update query_edit_modal.py: hint footer for agents-tab call site, parse-on-Apply with inline error rendering. Update help_modal/ with Agent Query Syntax cheatsheet (57-char width). Optional highlighting.py mirroring query/highlighting.py. Tests: integration test for hierarchy preservation, parse-error fallback, cached-AST reuse; modal error snapshot.

## Notes

COMMIT: d6b2a5d8

## Dependencies

- **Depends on:** [sase-v.2](sase-v.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3872af5`](https://github.com/sase-org/sase/commit/3872af53d1546d1617c12d0c007ed1216101978c) | feat(agents-tab): wire structured query filters into TUI — phase 3 of agents-tab structured query filters (sase-v.3) | [sase-v.3](sase-v.3.md) | 2026-04-26 08:15:25 |
