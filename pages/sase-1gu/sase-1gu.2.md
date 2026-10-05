# Bead: sase-1gu.2 — \`sase instructions verify\`: observed-mode scoreboard and doctor group

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.2` · **Size:** medium
**Created:** 2026-10-05 15:52:20 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

scoreboard: build `sase instructions verify`. Pure Python parsers turn Claude transcripts and subagent transcripts, Codex rollouts, Grok `prompt_context.json` and `system_prompt.txt`, and Muse `session.jsonl` into per-session observations. agy is reported as unverifiable. Locate sessions from the newest SASE runs per provider (bounded index query, run cwd and time window, capped reads). Show contract, home, project, directive, native-full, foreign, and helper columns with `-j` JSON, and add the deep-only doctor group `instructions`. Fixture tests must reproduce the baseline table. Attach the live baseline JSON to the epic.

## Dependencies

- **Depends on:** [sase-1gu.1](sase-1gu.1.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1gu.5](sase-1gu.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.2/README.md) | [sase-1gu.2](sase-1gu.2.md) | 0 |
