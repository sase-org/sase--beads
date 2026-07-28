# Bead: sase-55.3 — Phase 3 — Invocation threading + provider translation

[Bead Pages](../README.md) / [sase-55](README.md) / sase-55.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-55.3`
**Created:** 2026-06-23 15:25:51 UTC · **Closed:** 2026-06-23 17:08:36 UTC
**Plan:** [202606/xprompt\_effort\_levels.md](https://github.com/sase-org/sase--plans/blob/main/202606/xprompt_effort_levels.md)

## Notes

COMMIT: 37bf2b57b

[2026-07-27T21:36:56Z · sase-a1.land] [2026-06-23T17:07:40Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 3 complete. Added LLMInvocationOptions(reasoning_effort, explicit) in types.py and resolve_effective_effort(directives) in config.py (explicit %effort/@effort > llm_provider.default_effort > None). Threaded options keyword (default None) through invoke_agent -> LLMProvider.invoke -> llm_invoke hookspec -> plugin manager -> all 5 providers, plus run_commit_finalizer so commit/fix follow-ups keep effort. New _effort_args.effort_cli_args() implements the explicit->raise / default->skip+warn contract; base invocation_option_args() defaults to []. Provider translation: Claude --effort (low/medium/high/xhigh/max), Codex -c model_reasoning_effort="<level>" (minimal/low/medium/high/xhigh), OpenCode --variant (all levels; verified flag exists upstream), agy+qwen unsupported (explicit raises, default skips). Env escape hatches (SASE_LLM_*_ARGS) preserved. Tests: tests/test_llm_provider_effort_invocation.py + tests/llm_provider/test_commit_finalizer_effort.py; updated existing invoke/temp-override assertions for new options kwarg. just check passes.

## Dependencies

- **Depends on:** [sase-55.1](sase-55.1.md) ✓
- **Depends on:** [sase-55.2](sase-55.2.md) ✓
- **Blocks:** [sase-55.4](sase-55.4.md) ✓
- **Blocks:** [sase-55.6](sase-55.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-55.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-55.3/README.md) | [sase-55.3](sase-55.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7535d98`](https://github.com/sase-org/sase/commit/7535d98b718faaa5489e7ea7bc447e210b3edff1) | feat(llm\_provider): translate reasoning effort into per-run CLI args (sase-55.3) | [sase-55.3](sase-55.3.md) | 2026-06-23 17:10:21 |
