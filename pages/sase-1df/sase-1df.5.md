# Bead: sase-1df.5 — sase-xprompt-lsp Jinja completion and hover

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.5` · **Size:** medium
**Created:** 2026-09-30 08:47:23 EDT · **Closed:** 2026-09-30 11:41:45 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

lsp: route in-tag positions to the engine ahead of every other completion surface, add `{`/`|` triggers that stay silent outside tags, derive the scope from the document path, render rich CompletionItems and hover, and document it in docs/editor.md.

## Notes

[2026-09-30T15:41:08Z · sase-1df.5] PROPOSED FOLLOW-UP: sase-core clippy gate red on clean base — 9 pre-existing `-D warnings` lints (nonminimal_bool, manual contains, collapsible if) in untouched files agent_runtime.rs, agent_scan/index/maintenance.rs, finalizer/run_view/decode.rs (x2), fleet_owner_facts.rs, provider_usage/mod.rs (x2), tool_run/store/receipt.rs, tool_run/store/triage.rs under clippy 1.95.0; full workspace `just check` cannot pass until these are fixed

[2026-09-30T15:41:45Z · sase-1df.5] LSP Jinja completion+hover done: in-tag engine routing, {/| triggers silent outside tags, path-derived prompt/xprompt scope (gitcommit excluded), rich CompletionItems, hover-first, docs/editor.md. Verified: 207 sase_xprompt_lsp lib tests pass (18 new jinja + 5 scope + trigger-char), new stdio test passes, cargo fmt and prettier clean, new code clippy-clean. Full workspace clippy gate is red on the clean base tree (pre-existing sase_core lints, see PROPOSED FOLLOW-UP note); unrelated agents unaffected (epic-symbols clean).

## Dependencies

- **Depends on:** [sase-1df.3](sase-1df.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1df.9](sase-1df.9.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.5/README.md) | [sase-1df.5](sase-1df.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9074b2a`](https://github.com/sase-org/sase-core/commit/9074b2ab396664090d23ea7c82389bf1151c3e01) | feat(xprompt-lsp): Jinja completion and hover via engine | [sase-1df.5](sase-1df.5.md) | 2026-09-30 11:45:54 EDT |
| sase | [`08c4e83`](https://github.com/sase-org/sase/commit/08c4e83cfa092c941da9354be7feea6f77063b94) | docs(editor): document LSP Jinja completion and hover | [sase-1df.5](sase-1df.5.md) | 2026-09-30 12:28:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1df.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.5/README.md

<!-- sase:referenced-by:end -->
