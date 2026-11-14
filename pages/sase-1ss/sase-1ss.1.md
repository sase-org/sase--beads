# Bead: sase-1ss.1 — Catalog Gemini 4 Hydrogen on Antigravity (sase)

[Bead Pages](../README.md) / [sase-1ss](README.md) / sase-1ss.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1cb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1cb.md) · **Assignee:** `sase-1ss.1` · **Size:** medium
**Created:** 2026-11-13 18:46:15 EST · **Closed:** 2026-11-13 19:45:46 EST
**Plan:** [202611/argon\_hydrogen\_support.md](https://github.com/sase-org/sase--plans/blob/main/202611/argon_hydrogen_support.md)

## Description

agy-hydrogen-catalog: in the sase repo, add the four Hydrogen slugs and their hydrogen4* aliases to the agy section of models.yml. Retext the stale Argon advisory to Pro/Ultra and move the broken agy tiers to Gemini 3.8 Flash. Teach short_model_name about hydrogen. Update the pinned tests, regenerate and hand-edit the agy docs, refresh any shifted ACE PNG goldens, and record the five research follow-ups.

## Notes

[2026-11-14T00:20:06Z · sase-1ss.1] PROPOSED FOLLOW-UP: feature: agy --effort passthrough. Upstream agy 1.5.8 accepts --effort low|medium|high|xhigh|max with base slugs. Needs per-model level maps (Argon has no xhigh), base slugs in the catalog, a CLI version gate, and a decision record partly superseding size-alias-effort-ladder.

[2026-11-14T00:20:23Z · sase-1ss.1] PROPOSED FOLLOW-UP: bug: refresh agy catalog drift. Add the Claude Opus/Sonnet 5.5 slugs agy now serves; prune or mark the Enterprise-only 3.7/3.6/3.5 Flash and 3.1 Pro rows; remove Claude 4.6 and GPT-OSS after their 2026-11-18 upstream removal. Possibly related to sase-1l4 (older catalog-reconciliation task from the Argon plan); land agent should triage overlap.

[2026-11-14T00:20:34Z · sase-1ss.1] PROPOSED FOLLOW-UP: feature: list concrete catalog models in shell --model completion. Project packaged models.yml through importlib.resources (fast path must not import sase.llm_provider); keep the five size aliases and offer bare and agy/-qualified forms; update model_source_path() for cache invalidation; reclassify --next-model as ValueKind.MODEL.

[2026-11-14T00:20:52Z · sase-1ss.1] PROPOSED FOLLOW-UP: bug: migrate stale agy/gemini-3.7-flash-high pins in sase/macros/reads.md (pinned by tests/test_macro_swarm_local_helpers.py), docs/reference/macros/directive-syntax.md and other doc examples, the tmux agy model example in src/sase/default_config.yml and src/sase/config/sase.schema.json, plus a chezmoi task for m_agy*, m_swarm, and tmux_ai_window.

[2026-11-14T00:21:03Z · sase-1ss.1] PROPOSED FOLLOW-UP: policy: once a Free account confirms access, promote Hydrogen into the agy tiers and/or the size-alias ladder. Also decide whether to catalog Carbon and Orchestrator (gemini-pro-orchestrator-g1-pro). Governed by decisions:size-alias-effort-ladder.

[2026-11-14T00:45:46Z · sase-1ss.1] agy-hydrogen-catalog complete and verified: Hydrogen slugs + hydrogen4* aliases catalogued, Argon advisory retexted to Pro/Ultra, tiers on 3.8 Flash, short_model_name knows hydrogen, pins updated (incl. 24-model visual sentinel), agy.md/models.md regenerated and hand-edited, 1 PNG golden updated and inspected, 5 follow-ups recorded as notes. sase tool run check a77026ed730c650e51675e65197cb914 green (exit 0, full suite after scoped escalation). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ss.2](sase-1ss.2.md) ✓ · ⧖ 2026-11-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ss.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ss.1.md) | [sase-1ss.1](sase-1ss.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf7a09f`](https://github.com/sase-org/sase/commit/cf7a09f15b485b8e1f0b9216b4707aab93f16a5b) | feat(sase-1ss.1): catalog Gemini 4 Hydrogen on Antigravity | [sase-1ss.1](sase-1ss.1.md) | 2026-11-13 19:52:07 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ss.1--1][1] | Verify phase scope before closing after green check | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ss.1.md

<!-- sase:referenced-by:end -->
