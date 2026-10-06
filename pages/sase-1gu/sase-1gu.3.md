# Bead: sase-1gu.3 — Grok root runs receive the directive and project AGENTS.md once via --rules

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.3` · **Size:** small
**Created:** 2026-10-05 15:52:22 EDT · **Closed:** 2026-10-06 07:40:48 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

grok-root: absorbs sase-1gj with a corrected fix. On every invocation cycle the Grok adapter passes `--rules` with a new Grok single-turn directive, plus the project root `AGENTS.md` text exactly once in SASE-managed projects (the directive alone elsewhere). Never pass the home layer or `--trust`, and never set GROK_CLAUDE_AGENTS_ENABLED. Add a 120 KiB argv guard, the sunset flag `grok_rules_delivery`, argv tests for both flag states, a live parse probe, a local canary, and Grok docs.

## Notes

[2026-10-05T20:01:53Z · sase-1gu.3] grok-root canary ok: session cafc000f-108f-4ef1-a1cb-86d4995b6f0f under sessions/%2Fhome%2Fbryan%2F.local%2Fstate%2Fsase%2Fworkspaces%2Fsase-org%2Fsase%2Fsase_13/ holds <human_rules> (18166 bytes) with the Grok directive marker exactly once and the project AGENTS.md H1 exactly once; prompt_context.json still has agents_md_files: [] (audience primary). Ran via get_provider("grok").invoke, model_tier=small (grok-4.6), reply CANARY_OK.

[2026-10-06T11:40:48Z · 0x6.w0--1] Landed commits 724f9ea9c2 + 10a2173a7c; this turn fixed the continuation-cycle test's class-level interrupt leak (instance write plus autouse reset) and made the directive name Grok's wait primitives (block_until_ms, get_command_or_subagent_output, spawn_subagent background:false, scheduler_create); canary in note #1; sase-1gj pointer note added. Verification: grok scope green (69 passed: rules, stream, invocation, core, metadata, instructions). sase tool run check (da520176e5af20f73d333984dbefafb8) exited 1 with only triaged unrelated failures (2 KNOWN symvision lints, 1 KNOWN provider-drain e2e, 1 FLAKY macro-terminology from docs/images infographic prompt) and no new failures.

## Dependencies

- **Blocks:** [sase-1gu.5](sase-1gu.5.md) ✓ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.3/README.md) | [sase-1gu.3](sase-1gu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`724f9ea`](https://github.com/sase-org/sase/commit/724f9ea9c204296569c103f4ca6ceaa118d5e509) | feat(llm-provider): add Grok provider core with docs and registry | [sase-1gu.3](sase-1gu.3.md) | 2026-10-05 16:04:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0x6.w0--1][1] | need plan section 4 bookkeeping after grok-root check | 1 |
| read-by | [agent:sase-1g4.6][2] | Identify the feature-flag rollout that causes the clean-base schema mismatch | 1 |
| read-by | [agent:sase-1gu.3][3] | Need phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x6.w0.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.6/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.3/README.md

<!-- sase:referenced-by:end -->
