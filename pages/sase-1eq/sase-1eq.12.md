# Bead: sase-1eq.12 — Finish the xprompt-to-macro core flip and land sase-1eq

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.land.md) · **Assignee:** `sase-1eq.12.land`
**Created:** 2026-10-05 10:21:52 EDT · **Closed:** 2026-10-06 10:19:20 EDT
**Plan:** [202610/land\_xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/land_xprompts_to_macros.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/land_xprompts_to_macros.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/land_xprompts_to_macros.md

<!-- sase:links:end -->

## Description

sase-core's check is green again after the contract flip, sase-core and sase no longer emit pre-flip xprompt wire spellings outside durable legacy readers and flag-gated sunset inputs, and the macro docs infographic shows macro names, so the sase-1eq land agent can close the rename epic.

## Notes

[2026-10-05T17:43:37Z · sase-1gt.land] DISCOVERED ISSUE: sase-1gt lander at master 1c9a2cd5df independently reproduces tests/test_macro_terminology.py::test_macro_docs_and_memory_avoid_xprompt_terms (1 failed, 3.25s). Proposing beads: sase-1gt.2 note #1, sase-1gt.3 note #1, sase-1gt.4 note #2. The causal infographic phase sase-1eq.12.3 commit b6114d4f95 added historical old-to-new xprompt labels in docs/images/macro-resolution-infographic.prompt.md without matching exact-line entries in tests/_macro_terminology_docs.py:_MACRO_DOCS_ALLOWLIST. The PNG is relabeled, but its prompt record now trips the rename guard. Reword the record with macro-only labels or classify exact historical lines in the allowlist and its category guard. This belongs to this still-active rename epic, not CI-repair epic sase-1gt; no new task.

[2026-10-06T12:35:25Z · sase-1eq.12.land] LANDING TRIAGE AND VERIFICATION (2026-10-06, sase 312f17dc3f/core b19690e3): read every note on .1/.2/.3 and this epic, approved plan, parent sase-1eq landing note #6, and phase commits d65f7246, b19690e3, b6114d4f95, 312f17dc3f. Core-green fixes canonical/retired local-helper keys, canonical output assertions, and mutex serialization of both catalog env-mutating tests. Key-flip removed layout xprompts/xprompt_sources, emits schema 7 and macro snippet/launch/proc vocabulary, and host moved pin to b19690e3. Post-start history reviewed on master/origin-master and core: newer enum/model/effort/plugin input types retain canonical macro env exports and Rust parity paths; no branch divergence. Remaining epic work found: (1) infographic prompt record has 11 unallowlisted retired-label lines, independently confirmed by executing the docs guard without pytest fixtures; (2) PNG SHA matches 7529a15d..., but visual comparison with b6114d4f95^ shows double-drawn/clipped discovery labels in rows 1/2/3/9/10/11; (3) core still has canonical retired-named locals/helpers/aliases and user-facing strings (macro_catalog Read/LayoutCollision errors, Accept xprompt completion, sase xprompt LSP initialized); (4) EditorSnippetEntryWire key changed but owning snippet catalog schema is still 1; (5) stdio timeout was put only around one diagnostics loop, leaving shared read_message unbounded. These are caused by or incomplete requirements of this rename and stay epic work in a medium tale. Every child PROPOSED FOLLOW-UP outcome: .2 note #1 Rich long-path delete assertion is duplicate sase-18v, +1 source/impact corroboration recorded (fresh local pytest could not reproduce runtime due unbuilt editable core); .2 note #2 infographic guard retained here, not a new task; .2 note #3 source pin portion resolved by host, advisory published-floor gap duplicated to sase-10d (+1) and release integration recorded on sase-1c1 because .14 still targets a too-old floor; release is not a prerequisite of local/dev landing and no new task; .3 note #1 generated-schema drift declined as resolved: compared current schema blocks against installed builtin catalog (plugin-qualified rows excluded), both match after intervening named-input-type changes. No new task beads. No epic-symbol entries for this epic. Fresh workspace editable core has no built extension, so full local verification must start with just install after coding; global sase core health is OK. Do not close until the remaining tale implements, verifies, and performs this epic and ready parent closeout in the same turn.

[2026-10-06T14:19:20Z · sase-1eq.12.land--3] LANDING VERIFICATION (2026-10-06): all 3 phases closed (.1 core-green, .2 key-flip, .3 infographic). Repairs this tale: core canonical terminology + snippet schema 2 (core EDITOR_SNIPPET_CATALOG_WIRE_SCHEMA_VERSION=2, sase mirror, bounded stdio read, rebuilt infographic SHA 11d309a60628f3e9f356b2f7bc1dc46eb1ba3a9e871c783612c079a022ab55f2 prompt-record canonical-only, nvim unchanged as LSP consumer). Post-start integration reviewed: named enum/model/effort + plugin input types (sase 8fc4b4ccd6/1a2dc5e4dd/55c46c3633/abcfedc31d/81eaae59ea, core 16095fcf/af5df614) preserved, SASE_MACRO_PLUGIN_INPUT_TYPES_JSON intact. Verification: core sase tool run check passed; sase just install + just fix passed; final sase tool run check verdict no_new_failures (run f242708ade1167a6181fbf6f7051ec65) after fixing 3 epic-caused fixtures at root cause (missed macros/foo.md expectation, candidates fixture to canonical macro/macro_name wire, terminology pin table updated; no test weakened). Targeted snippet/helper/catalog/LSP/named-input-type suites green; both terminology sweeps green; sase core health ok. Follow-ups: Rich long-path delete dup sase-18v (+1 recorded, not reproduced locally); infographic prompt guard retained as epic work and done; published-floor blocked_unpublished stays advisory with sase-10d (not a landing gate); .3 schema drift declined as resolved. epic-symbols clean.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.12.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.12.land.md) | [sase-1eq.12](sase-1eq.12.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a62699b`](https://github.com/sase-org/sase-core/commit/a62699bb4224823293db49f8e2aa73427aa74ddf) | feat(macros)!: emit canonical macro wires and snippet catalog schema 2 | [sase-1eq.12](sase-1eq.12.md) | 2026-10-06 10:24:12 EDT |
| sase | [`17c7f66`](https://github.com/sase-org/sase/commit/17c7f66bb3be196d55eeefacdfc547340a138c48) | feat(macros): finish snippet schema-2 mirrors and canonical snippet fixtures | [sase-1eq.12](sase-1eq.12.md) | 2026-10-06 10:29:31 EDT |
| sase--plans | [`sase--plans@6b3d5fe`](https://github.com/sase-org/sase--plans/commit/6b3d5fee16045eff99793d28b37bf004cb87b811) | docs(plans): mark macro rename landing plans done | [sase-1eq.12](sase-1eq.12.md) | 2026-10-06 10:33:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.12.land--3][1] | Need final landing readiness | 1 |
| read-by | [agent:sase-1gt.land][2] | Need active causal epic before routing infographic terminology regression | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.12.land.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gt.land/README.md

<!-- sase:referenced-by:end -->
