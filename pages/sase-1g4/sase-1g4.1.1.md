# Bead: sase-1g4.1.1 — One input-type vocabulary and strict enum declarations

[Bead Pages](../README.md) / [sase-1g4.1](sase-1g4.1.md) / sase-1g4.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) · **Assignee:** `sase-1g4.1.1.land`
**Created:** 2026-10-04 18:33:14 EDT · **Closed:** 2026-10-05 02:04:39 EDT
**Plan:** [202610/macro\_input\_type\_vocab.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_input_type_vocab.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/macro_input_type_vocab.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/macro_input_type_vocab.md

<!-- sase:links:end -->

## Description

Macro inputs resolve through one sase-core catalog, unknown types and bad enum declarations fail per macro, and #pr status is a real enum.

## Notes

[2026-10-05T05:28:37Z · sase-1g4.1.1.land] LANDING TRIAGE before the loader tale. Verified phases sase-1g4.1.1.1 through sase-1g4.1.1.4 against source. Rust catalog, resolver, and Python bindings are in pinned sase-core 0279de6b (ancestor of 2838c7eb). Rust parsers, frontmatter diagnostics, schemas, config.macro_input_types, #pr status enum, and docs are landed. Python parse_input_type still silently maps unknown names to line, InputChoice has no description, InputArg has no named_type or value_role, validate_enum_choices is not called at load, per-macro isolation is missing, strict_macro_input_types does not exist, and handoff JSON omits the new fields. That unfinished loader work is the tale, not a new task.

Follow-ups:
- sase-1g4.1.1.2 prompt-catalog flake test_prompt_source_token_changes_for_project_file: declined. Reproduced on clean 25cc3c475d and fixed by 404b0e2ac2 (sase-1eq.5.1.6), an ancestor of HEAD. No task names that node.
- sase-1g4.1.1.3 pin ratchet to 2838c7eb: declined. Pin 0279de6b from dc8aee0fbc (sase-1eq.10) already contains the macro_input_types bindings. Do not rename local_xprompts; sase-1eq.10 still owns that.
- sase-1g4.1.1.3 note #3 and sase-1g4.1.1.4 note #1 loader integration: remaining epic work, planned as a medium tale. Not filed as a task.
- test_cancel_saves_once_submit_path_quiet: filed ready flake sase-1gg (large). Same missing-widget class as sase-1fy and sase-1g5, different node. sase-j7 note #85 already records it; not a confirmed process-global leak, so no second epic note.
- test_sudo_runner_invocation_keeps_canary_out_of_process_argv_and_env: filed ready flake sase-1gh (large). Different node from ready sibling sase-19d. sase-j7 note #86 already records it.
- test_agent_run_stops_on_a_new_item: filed ready flake sase-1gi (large). Closed sase-114 fixed a different nested-diagnostics leak. sase-j7 note #86 already records it.

Integration since the epic started, excluding this epic's commits: 362f737186 is unrelated test splitting. 404b0e2ac2 and cddd30c515 are the terminology sweep and its allowlist; the tale edits the post-sweep TUI callers. dc8aee0fbc moved the core pin forward and dropped dual macro env spellings; handoff still uses the local_xprompts JSON key and the tale adds fields beside it.

[2026-10-05T06:04:39Z · sase-1g4.1.1.land] Verified Rust/Python macro input catalog parity, strict_macro_input_types on/off behavior, per-macro isolation for bad enum declarations, #pr status wip | draft | ready, feature-flag schema sync, and handoff round-trips for choices, descriptions, repeatable, named_type, and value_role (159 focused tests passed). The direct Symvision scan passed. Full sase tool run check and the just symvision wrapper stop in _setup on clean linked sase-core 0279de6b: the unchanged SASE probe expects sase_content_layout schema 5 but receives 6, and the agent-stats macro probe rejects the current core response; setup stops before lint/test stages. This is outside the loader diff and the core pin remains untouched. Follow-up triage: prompt-catalog flake declined as fixed by 404b0e2ac2 / sase-1eq.5.1.6; pin ratchet declined because 0279de6b already contains the bindings from dc8aee0fbc / sase-1eq.10; loader notes from phases .1.1.3 and .1.1.4 are this tale; flakes are already filed as sase-1gg, sase-1gh, and sase-1gi (sase-j7 notes #85/#86), with no new tasks.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.1.land.md) | [sase-1g4.1.1](sase-1g4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`95291ab`](https://github.com/sase-org/sase/commit/95291ab31a447dcb720dcbdf1b87ae21590f2968) | feat(macros): wire loaders through input type catalog | [sase-1g4.1.1](sase-1g4.1.1.md) | 2026-10-05 02:10:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.1.1.1][1] | Need the parent epic scope and design details | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.1.1.1/README.md

<!-- sase:referenced-by:end -->
