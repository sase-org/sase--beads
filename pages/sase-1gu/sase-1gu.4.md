# Bead: sase-1gu.4 — Claude native helpers get a helper template and a root-only PreToolUse guard

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.4` · **Size:** medium
**Created:** 2026-10-05 15:52:23 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

claude-helpers: on every Claude invocation cycle, pass a packaged static helper template through the hidden `--append-subagent-system-prompt-file`, gated by a cached no-API capability probe. Also pass inline `--settings` JSON with a stdlib-only PreToolUse guard on Bash|Skill. When the hook input carries `agent_id`, the guard denies `sase final context|defer|prepare|submit`, turn-ending CLI commands, and root-only skills. Add the sunset flag `claude_helper_channel`, the doctor deep check `providers.claude_helper_channel`, tests, and raw mechanism probes: deny under bypass mode, the Explore and general-purpose markers, and whether forks carry `agent_id`.

## Dependencies

- **Blocks:** [sase-1gu.5](sase-1gu.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.4/README.md) | [sase-1gu.4](sase-1gu.4.md) | 0 |
