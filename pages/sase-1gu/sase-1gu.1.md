# Bead: sase-1gu.1 — The \`sase instructions\` command group absorbs \`sase memory agent-docs\`

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.1` · **Size:** small
**Created:** 2026-10-05 15:52:19 EDT · **Closed:** 2026-10-05 16:35:57 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

cli-group: add the top-level `sase instructions` group. Its `list` subcommand, also the bare-group default, is today's `sase memory agent-docs list` inventory, unchanged. Delete the `agent-docs` subcommand, then update the parser registries, entry dispatch, completion snapshot, tests, and docs (cli.md, configuration.md, init.md).

## Notes

[2026-10-05T20:35:36Z · sase-1gu.1] PROPOSED FOLLOW-UP: tests/test_macro_terminology.py::test_macro_docs_and_memory_avoid_xprompt_terms fails on xprompt residuals in docs/images/macro-resolution-infographic.prompt.md (11 lines); check triage marks it KNOWN with witness 4378e799592632616eb699362f69373d, no owner; unrelated to cli-group change

[2026-10-05T20:35:57Z · sase-1gu.1] cli-group done: new sase instructions group (parser_instructions.py + instructions_handler.py, registered in both parser registries, alphabetical dispatch in entry.py); sase instructions and sase instructions list print the Agent Documents panels with bare-default delegation notice; sase memory agent-docs is an argparse error; completion snapshot regenerated; tests moved to tests/main/test_instructions_group.py with parser-defaults/help tests updated; docs updated (cli.md, init.md, configuration.md, memory.md, inventory docstrings). Verified: 61 focused tests pass; sase tool run check: 52729 passed, only failure is the KNOWN macro-terminology infographic residual (recorded as PROPOSED FOLLOW-UP), triage verdict no_new_failures.

## Dependencies

- **Blocks:** [sase-1gu.2](sase-1gu.2.md) ✓ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.1/README.md) | [sase-1gu.1](sase-1gu.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8071b49`](https://github.com/sase-org/sase/commit/8071b49282a7642d0eab85a97fe8f65bbf179a92) | feat(cli)!: add sase instructions group absorbing memory agent-docs | [sase-1gu.1](sase-1gu.1.md) | 2026-10-05 16:37:13 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gu.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.1/README.md

<!-- sase:referenced-by:end -->
