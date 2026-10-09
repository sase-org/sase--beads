# Bead: sase-1if.4 — Plugin subtrees in completion with plugin-aware cache identity

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.4` · **Size:** medium
**Created:** 2026-10-08 15:26:24 EDT · **Closed:** 2026-10-08 21:47:41 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

completion: merge separately walked plugin parsers into a runtime completion spec, make the grammar and TUI spec caches key on the plugin command set and editable sources, and record omitted subtrees.

## Notes

[2026-10-09T01:47:41Z · 5y--1] Phase complete. Remaining work: grammar.py unkeyed-handle baseline adoption + private _command_line_grammar_spec_key_for; plugin_runtime _RuntimeCompletionSpec; snapshot.py symvision pragma; new test_plugin_runtime cases + docs/completion.md sentence. Check ToolRun f508ad2382d20ed506782bf45893c0be timed out at 1h monitor budget (exit -9, verdict undetermined); triage 48 KNOWN / 0 NEW, none touching completion/grammar files. Targeted verification: tests/completion/test_plugin_runtime.py 16 passed; tests/completion + contract 358 passed with 2 failures (test_zsh_smoke alias_sbd capture timeout, contract snippet CPU-budget) both reproduced on stashed base => pre-existing, unrelated. just check escalates to full suite per tools/select_tests; full re-verification routed to prepared-completion monitor.

## Dependencies

- **Depends on:** [sase-1if.1](sase-1if.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.5](sase-1if.5.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1if.4.md) | [sase-1if.4](sase-1if.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7922974`](https://github.com/sase-org/sase/commit/79229740620312e2be8412024ece417ca03f1998) | feat(completion): merge plugin parsers into runtime spec with plugin-aware cache identity | [sase-1if.4](sase-1if.4.md) | 2026-10-08 17:55:41 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:5y--2][1] | finish verification after timed-out check monitors | 1 |
| read-by | [agent:sase-1if.4--1][2] | Need phase scope for check report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5y.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1if.4.md

<!-- sase:referenced-by:end -->
