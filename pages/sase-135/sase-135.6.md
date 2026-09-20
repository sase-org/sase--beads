# Bead: sase-135.6 — Teach the tool workflow and measure its adoption

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.6` · **Size:** medium
**Created:** 2026-09-18 22:19:24 EDT · **Closed:** 2026-09-20 06:53:27 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

## Description

agent-adoption: Implement section 6, including docs/tool.md, the lint_and_test memory update, Tool Run and Tool Catalog glossary strands, monitor skill source guidance, compact root help, and the read-only adoption report.

## Notes

[2026-09-20T10:52:34Z · sase-135.6] PROPOSED FOLLOW-UP: move tool_adoption_report pairing/classification/aggregation into sase-core Rust — the plan says Rust owns the reusable logic; this phase shipped it in Python (tools/tool_adoption_report) to avoid a cross-repo change.

[2026-09-20T10:53:00Z · sase-135.6] PROPOSED FOLLOW-UP: mypy (20 no-untyped-def errors in src/sase/main/ace_tmux*.py) and symvision (_TmuxWindow, _WebSelector) fail at clean HEAD, so just check is red independent of this phase.

[2026-09-20T10:53:27Z · sase-135.6] Added docs/tool.md + nav, compact root help entry for tool (test updated), lint_and_test tool-run guidance, glossary tool-run/tool-catalog strands (sase memory init --check ok), sase_monitor skill source (previewed via sase skill init --diff), tools/tool_adoption_report + just tool-adoption + fixture tests. Baseline 7d: 654 raw heavy just-check calls, 0 wrapped, 194 ambiguous. Related pytest/ruff/pyscripts/keep-sorted pass; mypy+symvision fail at clean HEAD unrelated. Report is Python, not Rust (follow-up noted).

## Dependencies

- **Depends on:** [sase-135.5](sase-135.5.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-135.7](sase-135.7.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.6/README.md) | [sase-135.6](sase-135.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9cfb06a`](https://github.com/sase-org/sase/commit/9cfb06a548aefb28f04ea408eae0ce5c01d95d8d) | docs(tool): teach the named-tool workflow and add adoption report | [sase-135.6](sase-135.6.md) | 2026-09-20 06:55:42 EDT |
