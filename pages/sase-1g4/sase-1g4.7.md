# Bead: sase-1g4.7 — Dogfood, documentation, and memory

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.7` · **Size:** medium
**Created:** 2026-10-04 18:19:39 EDT · **Closed:** 2026-10-05 19:47:08 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

adopt: ship sase-research-artifacts' audio_edition type and move research_swarm's model inputs to type model, type sase's own macros, rewrite the docs input-type section around the one rule, update the macros.md memory Inputs line, and add an end-to-end parity test across runtime, LSP, and TUI.

## Notes

[2026-10-05T23:46:14Z · sase-1g4.7] Record unrelated check failures as follow-up PROPOSED FOLLOW-UP: test_macro_docs_and_memory_avoid_xprompt_terms fails on docs/images/macro-resolution-infographic.prompt.md xprompt residuals (our docs/macros.md and memory were not in the findings). --no-links -r

[2026-10-05T23:46:34Z · sase-1g4.7] Record grok stream check failures PROPOSED FOLLOW-UP: scoped just check NEW/KNOWN grok stream failures (test_grok_provider_replays_no_tool_fixture_and_accumulates_usage, test_grok_provider_replays_tool_fixture_and_writes_grok_artifacts, KNOWN test_grok_provider_error_fixture_surfaces_errors_array) plus KNOWN symvision _runs imports — none touch named input types. --no-links -r

[2026-10-05T23:47:08Z · sase-1g4.7] Shipped adopt-phase named input types.

Plugin: added sase_research_artifacts/input_types.yml (audio_edition brief/full), typed research_audio edition and research_swarm nine *_model plus audio_edition; YAML ships in wheel/sdist; older sase degrades unknown types to line (no version floor). Plugin sase tool run check passed.

sase macros: scanned src/sase/macros/; pr.yml status is already enum; remaining word inputs are names, VCS prefixes, and free labels, not models/efforts/closed sets.

Docs: rewrote docs/macros.md Typed Inputs around scalar→enum→builtin→plugin, added sase macro types (seven CLI subcommands), updated workflow_spec.md and editor.md cross-links. Memory Inputs line updated via sase memory init.

Parity: tests/macro/test_named_input_type_parity.py fixture with inline enum, effort, model, and plugin type; runtime binder, LSP diagnostics, and TUI candidates accept/reject the same values (4 passed).

Must-pass: #research_swarm(claude_model=opsu) binds with did-you-mean `opus`; #research/audio:breif rejects with did-you-mean `brief`; sase doctor -C config.macro_input_types is clean. Flag bead sase-1g9 exists (open sunset, remove-by 2027-01-02 / 0.19.0). epic-symbols: none leftover.

sase scoped check: KNOWN symvision _runs imports and grok error fixture; NEW grok stream + xprompt infographic prompt residuals recorded as PROPOSED FOLLOW-UP (not caused by this phase).

## Dependencies

- **Depends on:** [sase-1g4.5](sase-1g4.5.md) ✓ · ⧖ 2026-10-04
- **Depends on:** [sase-1g4.6](sase-1g4.6.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.7/README.md) | [sase-1g4.7](sase-1g4.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`abcfedc`](https://github.com/sase-org/sase/commit/abcfedc31d7b71f6bb2fa72fbc6e58d7f49e2b70) | feat(macros): document named input types and add runtime/LSP/TUI parity | [sase-1g4.7](sase-1g4.7.md) | 2026-10-05 19:49:38 EDT |
| sase-research-artifacts | [`sase-research-artifacts@bea92af`](https://github.com/sase-org/sase-research-artifacts/commit/bea92afb713db71c666a4f62ea53c4652460e2c4) | feat(macros): ship audio\_edition type and type research model inputs | [sase-1g4.7](sase-1g4.7.md) | 2026-10-05 19:53:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.7][1] | Need notes and extra fields for sase-1g4.7 | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.7/README.md

<!-- sase:referenced-by:end -->
