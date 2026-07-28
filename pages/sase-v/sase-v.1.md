# Bead: sase-v.1 — Phase 1 — agent\_query/ skeleton: types, tokenizer, parser

[Bead Pages](../README.md) / [sase-v](README.md) / sase-v.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-v.1`
**Created:** 2026-04-26 07:30:53 UTC · **Closed:** 2026-04-26 07:47:11 UTC
**Plan:** [202604/agents\_tab\_query\_filters.md](https://github.com/sase-org/sase--plans/blob/main/202604/agents_tab_query_filters.md)

## Description

Pure-syntax layer. Create src/sase/ace/agent_query/ package with __init__.py, types.py (StringMatch, NotExpr, AndExpr, OrExpr, PropertyMatch, DurationCompare), tokenizer.py (closed property-key allowlist, age comparison operators, duration literals, boolean literals), and parser.py (recursive descent, NOT > AND > OR precedence, AgentQueryParseError). Tests under tests/ for tokenizer, parser, and canonicalization round-trip. No semantics, no Agent imports, no TUI touches.

## Notes

COMMIT: 47ee8390

## Dependencies

- **Blocks:** [sase-v.2](sase-v.2.md) ✓
