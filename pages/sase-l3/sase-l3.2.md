# Bead: sase-l3.2 — Grok tool-call normalizer

[Bead Pages](../README.md) / [sase-l3](README.md) / sase-l3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.2` · **Size:** medium
**Created:** 2026-08-13 14:41:24 EDT · **Closed:** 2026-08-13 17:01:08 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

tools: add `_tool_call_grok.py` mapping Grok's snake_case tool names and JSON-string tool_result envelopes onto SASE's canonical display names and structured summaries so ACE Tools rows show real commands and paths.

## Notes

[2026-08-13T21:01:08Z · sase-l3.2] Implemented Grok tool-call normalizer/export with ACE reader coverage for Bash command+exit, search_replace path, unmapped tools, and non-JSON result fallback; verified targeted pytest for Grok/Qwen/Claude messages plus just check.

[2026-08-13T21:02:54Z · sase-l3.2] Verified Grok tool-call normalization with focused pytest coverage and just check.

## Dependencies

- **Depends on:** [sase-l3.1](sase-l3.1.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-l3.3](sase-l3.3.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.2/README.md) | [sase-l3.2](sase-l3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d36d6d`](https://github.com/sase-org/sase/commit/4d36d6d3d6632859ddc5cf78ab9f621f9cc92ccb) | feat: normalize Grok tool-call stream artifacts | [sase-l3.2](sase-l3.2.md) | 2026-08-13 17:04:01 EDT |
