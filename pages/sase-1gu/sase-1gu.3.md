# Bead: sase-1gu.3 — Grok root runs receive the directive and project AGENTS.md once via --rules

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.3` · **Size:** small
**Created:** 2026-10-05 15:52:22 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

grok-root: absorbs sase-1gj with a corrected fix. On every invocation cycle the Grok adapter passes `--rules` with a new Grok single-turn directive, plus the project root `AGENTS.md` text exactly once in SASE-managed projects (the directive alone elsewhere). Never pass the home layer or `--trust`, and never set GROK_CLAUDE_AGENTS_ENABLED. Add a 120 KiB argv guard, the sunset flag `grok_rules_delivery`, argv tests for both flag states, a live parse probe, a local canary, and Grok docs.

## Notes

[2026-10-05T20:01:53Z · sase-1gu.3] grok-root canary ok: session cafc000f-108f-4ef1-a1cb-86d4995b6f0f under sessions/%2Fhome%2Fbryan%2F.local%2Fstate%2Fsase%2Fworkspaces%2Fsase-org%2Fsase%2Fsase_13/ holds <human_rules> (18166 bytes) with the Grok directive marker exactly once and the project AGENTS.md H1 exactly once; prompt_context.json still has agents_md_files: [] (audience primary). Ran via get_provider("grok").invoke, model_tier=small (grok-4.6), reply CANARY_OK.

## Dependencies

- **Blocks:** [sase-1gu.5](sase-1gu.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.3/README.md) | [sase-1gu.3](sase-1gu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`724f9ea`](https://github.com/sase-org/sase/commit/724f9ea9c204296569c103f4ca6ceaa118d5e509) | feat(llm-provider): add Grok provider core with docs and registry | [sase-1gu.3](sase-1gu.3.md) | 2026-10-05 16:04:16 EDT |
