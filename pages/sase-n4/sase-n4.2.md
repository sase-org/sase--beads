# Bead: sase-n4.2 — Runtime disable and retry precedence

[Bead Pages](../README.md) / [sase-n4](README.md) / sase-n4.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03j.md) · **Assignee:** `sase-n4.2` · **Size:** medium
**Created:** 2026-08-16 10:34:06 EDT
**Plan:** [202608/llm\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/llm_usage_limit_auto_disable.md)

## Description

enforce: call detection from the LLM invocation error paths, write the temporary provider disable through the existing Rust-backed store with a structured source, make a usage-limit failure take precedence over the retry loop so agents stop sleeping through futile waits, and record telemetry.

## Dependencies

- **Depends on:** [sase-n4.1](sase-n4.1.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n4.3](sase-n4.3.md) ◐ · ⧖ 2026-08-16
- **Blocks:** [sase-n4.4](sase-n4.4.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.2/README.md) | [sase-n4.2](sase-n4.2.md) | 0 |
