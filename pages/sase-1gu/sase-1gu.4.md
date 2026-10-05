# Bead: sase-1gu.4 — Claude native helpers get a helper template and a root-only PreToolUse guard

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.4` · **Size:** medium
**Created:** 2026-10-05 15:52:23 EDT · **Closed:** 2026-10-05 17:11:29 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

claude-helpers: on every Claude invocation cycle, pass a packaged static helper template through the hidden `--append-subagent-system-prompt-file`, gated by a cached no-API capability probe. Also pass inline `--settings` JSON with a stdlib-only PreToolUse guard on Bash|Skill. When the hook input carries `agent_id`, the guard denies `sase final context|defer|prepare|submit`, turn-ending CLI commands, and root-only skills. Add the sunset flag `claude_helper_channel`, the doctor deep check `providers.claude_helper_channel`, tests, and raw mechanism probes: deny under bypass mode, the Explore and general-purpose markers, and whether forks carry `agent_id`.

## Notes

[2026-10-05T20:08:10Z · sase-1gu.4] Raw mechanism probes (2026-10-05, claude 2.1.289, haiku, scratch /tmp/sase-probe-1, adapter argv with --settings guard shim + --append-subagent-system-prompt-file template, SASE_* env scrubbed): (a) exit-0 JSON deny BLOCKS under --dangerously-skip-permissions (permission_mode bypassPermissions) - helper received "SASE helper guard: blocked sase final submit..."; no exit-2 fallback needed. (b) general-purpose + Explore helpers both carry agent_id in hook input; both subagent transcripts contain the "# SASE Helper Instructions" marker. Root calls carry no agent_id and are never denied (root sase final submit executed, failed harmlessly on manifest validation). Benign helper Bash (echo) allowed. (c) forked (depth-2 nested Explore) helper carries agent_id - guard covers forks. Guard latency: mean 23.4ms, p95 32.0ms (target <100ms).

[2026-10-05T20:49:22Z · sase-1gu.4] PROPOSED FOLLOW-UP: tests/test_macro_terminology.py::test_macro_docs_and_memory_avoid_xprompt_terms fails identically on clean HEAD (verified in pristine worktree of 8fc4b4ccd6) - stale xprompt lines in docs/images/macro-resolution-infographic.prompt.md, untouched by this phase; needs allowlist entry or prompt-file rename

[2026-10-05T21:11:29Z · sase-1gu.4] claude-helpers done and verified: packaged helper template via --append-subagent-system-prompt-file (cached no-API probe), inline --settings PreToolUse guard keyed on agent_id, sunset flag claude_helper_channel (bead sase-1gw) + doctor deep check providers.claude_helper_channel, docs in llms.md/agent_providers.md. Tests: 98 passed/1 skipped across helper guard+channel, claude hooks/core/wait-guard, doctor command (3 wait-guard tests isolate the probe spawn like usage capture). Live probes (haiku, adapter argv): exit-0 JSON deny blocks under bypassPermissions; gp+Explore helpers carry agent_id and see the template marker; nested forks carry agent_id; guard p95 32ms. just check triage: no_new_failures - sole failure is pre-existing macro-terminology xprompt (reproduces on clean HEAD, recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1gu.5](sase-1gu.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.4/README.md) | [sase-1gu.4](sase-1gu.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`421c3ba`](https://github.com/sase-org/sase/commit/421c3ba045b9f7376c4f5bc05eb6c01d4acfdaf7) | feat(claude): add helper guard and channel with sunset flag | [sase-1gu.4](sase-1gu.4.md) | 2026-10-05 17:13:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gu.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.4/README.md

<!-- sase:referenced-by:end -->
