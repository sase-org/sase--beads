# Bead: sase-tj.10.1 — Make \`sase agent search\` accept its options after the query

[Bead Pages](../README.md) / [sase-tj.10](sase-tj.10.md) / sase-tj.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.md) · **Assignee:** `sase-tj.10.1` · **Size:** small
**Created:** 2026-08-25 15:02:46 EDT · **Closed:** 2026-08-25 15:22:31 EDT
**Plan:** [202608/agent\_pane\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pane_landing_gaps.md)

## Description

cli_options: replace the positional QUERY's nargs=REMAINDER, which swallows -j/-l/-p into the query text, and add argv-level tests that exercise the real parser instead of a hand-built Namespace.

## Notes

[2026-08-25T19:22:31Z · sase-tj.10.1] Replaced nargs=argparse.REMAINDER with nargs="*" on the query positional in parser_agent_search.py, so -j/-l/-p parse correctly both before and after the query (verified: 'sase agent search kind:family -l 3' now exits 0 instead of raising a tokenizer error at position 61). Added 4 argv-level tests through create_parser(only="agent")/register_agent_search_parser (not hand-built Namespaces): options-before-and-after-query parsing, a regression test for the exact failing invocation, an options-after-query handle_agents_search test, and a test confirming the boolean dialect has no leading-dash query spelling (so no -- epilog doc was needed). just check passed clean (all lint gates + scoped test lane, exit 0). No epic-symbol entries for this phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tj.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tj.10.1/README.md) | [sase-tj.10.1](sase-tj.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba8a9cc`](https://github.com/sase-org/sase/commit/ba8a9cc75d0e50442257f01ef9b5a7aec5d9b7b9) | fix(agent-search): let \`sase agent search\` accept -j/-l/-p after the query | [sase-tj.10.1](sase-tj.10.1.md) | 2026-08-25 15:23:29 EDT |
