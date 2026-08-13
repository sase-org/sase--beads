# Bead: sase-l3.1 — Provider-neutral Messages-wire stream layer

[Bead Pages](../README.md) / [sase-l3](README.md) / sase-l3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.1` · **Size:** medium
**Created:** 2026-08-13 14:40:48 EDT · **Closed:** 2026-08-13 15:17:19 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

wire: generalize the Claude stream-json parser into a provider-parameterized Anthropic-Messages reader — runtime tagging, `errors[]` diagnostics, a thinking-block sink, and a pluggable tool-call writer seam — leaving Claude behavior byte-identical.

## Notes

[2026-08-13T19:06:04Z · sase-l3.1--1] PROPOSED FOLLOW-UP: Clean stale Symvision epic-symbol entries for closed bead sase-kz.5 — just check currently stops in lint (symvision) before tests because the Justfile still whitelists SnippetSessionTransition/SnippetSpan/SnippetStop and snippet-session helper symbols for closed bead sase-kz.5.

[2026-08-13T19:17:19Z · sase-l3.1--1] Implemented provider-neutral Messages-wire stream parser: runtime decode diagnostics, pluggable tool-call writer, errors[] failure detail folding, optional thinking JSONL sink, and compatibility export while preserving the Claude wrapper. Verified .venv/bin/pytest tests/llm_provider/test_messages_wire.py and the nearby Claude/parser regression set (43 passed). Ran just check after changes: fmt, markdown fmt, Ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology passed; it failed at unrelated stale Symvision epic-symbol entries for closed bead sase-kz.5, recorded as PROPOSED FOLLOW-UP on this phase.

[2026-08-13T19:20:38Z · sase-l3.1--1] Post-close refinement: provider-neutral stream accepts thinking_sink=True for the built-in codex_thinking.jsonl writer, so the Grok provider can enable ACE reasoning without importing a private helper. Re-verified .venv/bin/pytest parser/Claude regression set (43 passed). Final just check again passed fmt, markdown fmt, keep-sorted, Ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed only at unrelated stale Symvision epic-symbol entries for closed bead sase-kz.5.

[2026-08-13T19:22:14Z · sase-l3.1--1] Verified focused Messages-wire/Claude parser regression set passed (43 tests); just check passed fmt, Ruff, mypy, and pre-Symvision gates, then failed only on unrelated stale sase-kz.5 Symvision exemptions.

## Dependencies

- **Blocks:** [sase-l3.2](sase-l3.2.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-l3.1.md) | [sase-l3.1](sase-l3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ad4ae62`](https://github.com/sase-org/sase/commit/ad4ae62aef705022872998254613c72e068a6d43) | feat(llm-provider): add provider-neutral messages parser | [sase-l3.1](sase-l3.1.md) | 2026-08-13 15:23:41 EDT |
