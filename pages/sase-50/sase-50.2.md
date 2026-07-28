# Bead: sase-50.2 — Phase 2: Core agy Provider

[Bead Pages](../README.md) / [sase-50](README.md) / sase-50.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-50.2`
**Created:** 2026-06-19 22:57:37 UTC · **Closed:** 2026-06-19 23:52:52 UTC
**Plan:** /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase\_10/sdd/plans/202606/agy\_provider\_mvp.md

## Notes

COMMIT: 63a6991b2

[2026-07-27T21:36:01Z · sase-a1.land] [2026-06-19T23:49:50Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 2 complete: plain-stdout MVP AgyProvider (Antigravity CLI).

Implemented:
- src/sase/llm_provider/agy.py (AgyProvider, LLMProvider subclass); entry point 'agy' in pyproject.toml [sase_llm].
- No structured agy contract (Phase 1 'Current Facts' + local agy 1.0.10 probe: no JSON/stream mode), so plain stdout via shared stream_process_output(); InvokeResult(usage=None). Tool-call/usage/thinking artifacts intentionally unsupported in MVP.
- Tier defaults: large='Gemini 3.5 Flash (High)', small='Gemini 3.5 Flash (Low)'. Known models = exact 'agy models' display names (with spaces/parens) + compact short aliases.
- Metadata: short name 'agy', skill deploy subpath '.gemini/antigravity-cli', cli color #6E5DE7 (not Gemini blue), autodetect cli 'agy' priority 30 (old gemini slot).
- argv command (no shell): agy --print-timeout <dur> --model <m> --dangerously-skip-permissions --print <prompt>. Env precedence SASE_LLM_{LARGE,SMALL}_ARGS before SASE_AGY_{LARGE,SMALL}_ARGS; SASE_AGY_PATH; SASE_AGY_PRINT_TIMEOUT (default 24h, provisional - agy builtin default 5m too short for agentic runs).
- Interrupt: start_interrupt_monitor + Qwen/OpenCode restart-with-accumulated-context.
- Tests: tests/test_llm_provider_agy.py (15) cover subclassing, tier/override, exact argv, env precedence, SASE_AGY_PATH, missing-exe, non-zero exit, interrupt-resume prompt, nested 'agy/Gemini 3.5 Flash (High)' resolution, fake-CLI live_reply capture, and no-shell-interpolation with quotes/newlines/tabs.
- Skills (per Q1 'generate locally, no push'): ran 'sase skill init --force --no-push' -> 13 agy SKILL.md generated, committed to local chezmoi (no push), chezmoi apply'd to ~/.gemini/antigravity-cli/skills/. init --check / sase validate now green.
- Fixed 2 model-picker tests broken by agy 'Gemini ...' models now matching the 'gemini' filter.
- just check: ALL GREEN.

Deferred (later phases, NOT done here):
- Phase 3: registry _llm_metadata_cache_policy() env list still lacks SASE_AGY_PATH; doctor hints/retry config.
- Phase 4: 'sase skill init -p agy' still rejects 'agy' (hardcoded -p choices {claude,gemini,codex,opencode,qwen}); skill-init provider choices + tests.
- Phase 7: large-prompt argv length (single arg >~128KB E2BIG) untested - agy has no documented stdin prompt transport.

## Dependencies

- **Depends on:** [sase-50.1](sase-50.1.md) ✓
- **Blocks:** [sase-50.3](sase-50.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-50.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-50.2/README.md) | [sase-50.2](sase-50.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`86c8614`](https://github.com/sase-org/sase/commit/86c8614726acac65409a55ff39d7b43869294328) | feat(llm): add core Antigravity (agy) provider (MVP) (sase-50.2) | [sase-50.2](sase-50.2.md) | 2026-06-19 23:53:51 |
