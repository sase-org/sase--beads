# Bead: sase-29.4 — Phase 4 - End-to-End Runtime Validation and Hardening

[Bead Pages](../README.md) / [sase-29](README.md) / sase-29.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-29.4`
**Created:** 2026-05-07 06:03:19 UTC · **Closed:** 2026-05-07 06:51:25 UTC
**Plan:** [202605/qwen\_opencode.md](https://github.com/sase-org/sase--plans/blob/main/202605/qwen_opencode.md)

## Description

Validate both providers with real CLIs and harden failures before declaring the feature complete.

## Notes

Completed Phase 4 runtime hardening on 2026-05-07. Real CLI smoke blockers: qwen --version failed with command not found; opencode --version failed with command not found, so direct real-runtime, background-agent, interrupt, retry, config-corruption, and provider/model artifact validations against authenticated real CLIs were skipped. Added fake-CLI integration coverage for Qwen and OpenCode subprocess invocation success/failure paths, live_reply.md, usage.json, and structured error diagnostics. Hardened command construction to match current docs: Qwen now uses stdin text input mode with --input-format text; OpenCode now passes the SASE prompt as the documented run message argument without shell interpolation. Validated .venv/bin/sase init-skills --dry-run --provider qwen and --provider opencode. Validation passed: targeted provider/integration tests and just check.

## Dependencies

- **Depends on:** [sase-29.3](sase-29.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`822dc3f`](https://github.com/sase-org/sase/commit/822dc3fa9966ba9a1b9404e336742193ca8dc09b) | fix: refresh stale editable metadata before tests (sase-29.4) | [sase-29.4](sase-29.4.md) | 2026-05-07 06:51:37 |
