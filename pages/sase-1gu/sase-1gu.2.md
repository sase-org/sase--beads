# Bead: sase-1gu.2 — \`sase instructions verify\`: observed-mode scoreboard and doctor group

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.2` · **Size:** medium
**Created:** 2026-10-05 15:52:20 EDT · **Closed:** 2026-10-05 17:16:51 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

scoreboard: build `sase instructions verify`. Pure Python parsers turn Claude transcripts and subagent transcripts, Codex rollouts, Grok `prompt_context.json` and `system_prompt.txt`, and Muse `session.jsonl` into per-session observations. agy is reported as unverifiable. Locate sessions from the newest SASE runs per provider (bounded index query, run cwd and time window, capped reads). Show contract, home, project, directive, native-full, foreign, and helper columns with `-j` JSON, and add the deep-only doctor group `instructions`. Fixture tests must reproduce the baseline table. Attach the live baseline JSON to the epic.

## Notes

[2026-10-05T21:16:17Z · sase-1gu.2] PROPOSED FOLLOW-UP: just check _lint-flags fails identically on the clean base tree (live flag bead sase-1gw for claude_helper_channel from sase-1gu.4 has no definition yet); re-run check after sase-1gu.4 lands

[2026-10-05T21:16:33Z · sase-1gu.2] PROPOSED FOLLOW-UP: live codex baseline is 1x home-only (3 observed rollouts carry one native block matching the home H1) vs plan 2x; revisit after wider soak or E3 bundle lands

[2026-10-05T21:16:51Z · sase-1gu.2] scoreboard landed: verify CLI with -a/-H/-j/-n/-p/-s/-u, 5 pure parsers, doctor deep group instructions, 21 fixture tests pass, live baseline attached to sase-1gu (claude 2x, muse 1x no-home, grok 0; codex observed 1x explained in notes); only check failure (_lint-flags) reproduces on clean base via sibling sase-1gu.4

## Dependencies

- **Depends on:** [sase-1gu.1](sase-1gu.1.md) ✓ · ⧖ 2026-10-05
- **Blocks:** [sase-1gu.5](sase-1gu.5.md) ◐ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.2/README.md) | [sase-1gu.2](sase-1gu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`08c8a56`](https://github.com/sase-org/sase/commit/08c8a56b365119cc9ba962d9ebd6cf4be5113e12) | feat(instructions): add observed-mode instruction delivery verifier | [sase-1gu.2](sase-1gu.2.md) | 2026-10-05 17:18:38 EDT |
