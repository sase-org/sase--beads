# Bead: sase-1aa.5 — Finish model manifest parity cleanup and maintenance proof

[Bead Pages](../README.md) / [sase-1aa](README.md) / sase-1aa.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aa.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aa.land.md) · **Assignee:** `sase-1aa.5.land`
**Created:** 2026-09-26 08:43:36 EDT · **Closed:** 2026-09-26 11:13:21 EDT
**Plan:** [202609/finish\_model\_catalog\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_model_catalog_landing.md)

## Description

Remove the temporary migration snapshot and stale manual model lists, then prove that a synthetic built-in model update reaches every existing model surface through models.yml alone.

## Notes

[2026-09-26T15:13:21Z · sase-1aa.5.land] Verified all three closed phases against their notes, the source tree, and commits 6a6ae5d10 (snapshot removal), ec25a1a33 (prose refresh), and fedf207c1 (synthetic surface proof).

Phase 1: tests/llm_provider/_phase2_model_catalog_baseline.json is deleted. A repo search finds no remaining consumer in code, tests, or the Justfile.

Phase 2: docs/llms.md no longer keeps a second Automatic Provider Resolution catalog. README.md, docs/getting_started.md, docs/agent_providers.md, docs/ace.md, docs/configuration.md, and docs/llms.md now point pool membership, tier defaults, and current model names at the generated Built-in Model Catalog and shipped size-alias tables. Muse Contributor warnings remain without pinning today's pool membership. The only later edit to those files is e56510572, which rewords project-tag completion in docs/ace.md and does not restore a model list.

Phase 3: tests/test_manifest_synthetic_exercise.py derives one synthetic Claude model, a small-tier retune, and a medium-selector retune from shipped models.yml. It checks a clean second doc render and that registry hooks, routing, alias resolution, picker visibility, TUI completion, and model_completion_catalog_payload() observe the synthetic model. Focused pytest of that file plus test_render_model_docs.py, test_model_manifest.py, and test_model_policy.py: 41 passed.

Integration: commits on master between 6a6ae5d10 and fedf207c1 that are not this epic (sase-19x.8, sase-1ag.2, sase-1ab.2 fallout, node finder, receipt catalog, finalizer sidecar dirt, Services panels, receipt CLI, deck-panel split) do not reintroduce the parity snapshot or a hand-maintained model catalog, and none of them should call a new model-catalog API. No integration edit was required. sase bead epic-symbols sase-1aa.5 lists nothing.

Follow-ups:
- Symvision red on closed sase-19x.4 entries (phase_card_block, block_meta_for_session_shell, session_reply_heading), proposed by sase-1aa.5.1 #1, sase-1aa.5.2 #1, and sase-1aa.5.3 #1. Not caused by this epic. Reproduced with just symvision on clean master fedf207c1. The sase-19f entries named in those notes are already gone. sase-18i(CoderPlacement) and sase-18i(RetiredGate) were not rejected. Corroborated on task sase-o7 (+19) and appended a DISCOVERED ISSUE on in-progress epic sase-19x, whose notes #2-#5 already assign deleting the three lines to that land agent. The symbols already have non-test callers, so no new task was created.
- Monitored just check killed at the 60m budget (sase-1aa.5.3 #2). Declined. The new tests' call times are under a second, the kill is the monitor budget rather than a failing assertion, and the past week's task beads do not contain this signature. Not caused by this epic.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aa.5.land/README.md) | [sase-1aa.5](sase-1aa.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@91e2ac2`](https://github.com/sase-org/sase--plans/commit/91e2ac28b9a64d9d789dea93c29b35d5a05cda93) | docs(plans): mark model catalog landing plans done | [sase-1aa.5](sase-1aa.5.md) | 2026-09-26 11:20:05 EDT |
