# Bead: sase-29.1 — Phase 1 - Qwen Code Provider

[Bead Pages](../README.md) / [sase-29](README.md) / sase-29.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-29.1`
**Created:** 2026-05-07 06:02:58 UTC
**Plan:** [202605/qwen\_opencode.md](https://github.com/sase-org/sase--plans/blob/main/202605/qwen_opencode.md)

## Description

Add working first-class support for Qwen Code through the existing LLM provider plugin boundary.

## Notes

Phase 1 complete: added built-in qwen LLM provider entry point and QwenProvider using qwen -p - --output-format stream-json --yolo --model <model>, SASE_QWEN_PATH, tier-specific extra args, interrupt relaunch handling, Qwen stream-json parser coverage, docs, and init-skills provider support. Validation: just install; .venv/bin/pytest tests/test_llm_provider_qwen.py tests/llm_provider/test_usage_parsing.py -q; .venv/bin/sase init-skills --dry-run --provider qwen; just check. Manual qwen smoke skipped because qwen is not installed on PATH in this workspace.

## Dependencies

- **Blocks:** [sase-29.2](sase-29.2.md) ✓
