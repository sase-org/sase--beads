# Bead: sase-n8.9 — Acceptance against real agent history

[Bead Pages](../README.md) / [sase-n8](README.md) / sase-n8.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03t](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03t.md) · **Assignee:** `sase-n8.9` · **Size:** small
**Created:** 2026-08-16 11:33:35 EDT · **Closed:** 2026-08-16 18:07:47 EDT
**Plan:** [202608/launch\_control\_alias\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/launch_control_alias_history.md)

## Description

verify: exercise the panel against the real machine-local artifact index — a legacy-only alias, a freshly launched alias, a bucket, a truncated alias, and an alias with no runs — and confirm the migration backfilled without a full rebuild.

## Notes

[2026-08-16T22:07:47Z · sase-n8.9] Verified against the real machine-local index (/home/bryan/.sase/agent_artifact_index.sqlite, 7255 artifacts):
1) Migration: meta.schema_version=22; agent_artifact_model_aliases has 305 backfilled rows; indexed_at timestamps still span 2026-08-07..today (not reset), confirming a pure record_json re-projection with no filesystem rescan.
2) @large (legacy-heavy built-in alias, 34 runs): load_alias_history + the real rendering functions (alias_history_title_text/build_alias_history_rows/alias_history_detail_text) correctly show older rows as 'unrecorded' with the honest non-speculative detail-strip explanation.
3) Direct vs default: real dogfood data already includes both provenance kinds for @large (12 'direct' from %model:@large, 7 'default' from no-directive launches), both with full trail rendering (`@large → provider/model @effort · origin`).
4) Indirect (via-chain): no organic real launch has gone through a chained custom alias (research_lead -> @smartest) yet, so this could not be exercised against real data; the code path is covered by tests/llm_provider/test_alias_history.py and tests/test_alias_history_rendering.py (indirect classification, both passing). Not fixing/adding data myself since that would mean spawning a real agent purely for test purposes.
5) Bucket (researchers: research_a/research_b/research_lead): grouped headers + per-alias empty rows render correctly (all zero runs currently, real data).
6) Truncation: @medium_worker has 112 real runs, limit 10 -> returned=10/truncated=True; simulated Ctrl+K (limit=20) -> returned=20/truncated=True, confirming the paging query path.
7) Empty alias (@glm52_max) and empty bucket both render the first-run explanatory copy correctly.
8) Perf: load_alias_history against the real 7k-row index took 12-40ms per call (single alias, bucket, and doubled-limit re-query) — well within a background-worker load, no key-to-paint concern.
Also ran the full alias-history test surface (tests/test_alias_history_modal.py, _rendering.py, _state.py, tests/core/test_agent_alias_history_wire.py, tests/llm_provider/test_alias_history.py, tests/test_core_agent_scan_wire.py): 99 passed.
PNG visual snapshots: 2/5 alias-history goldens (empty, legacy_only) failed on <0.01% pixel diff, but this is pre-existing local font/renderer drift affecting the whole Models panel (42/43 unrelated Models-panel goldens also fail identically in this workspace) — not an alias-history regression, already covered by structural rendering checks above.
Did not touch the already-tracked footer 'History' hint test mismatch (3 failing tests in tests/test_models_panel_history.py) or make any code changes — that is already recorded on this epic multiple times as the land agent's responsibility to resolve before sase-n8 lands.

## Dependencies

- **Depends on:** [sase-n8.1](sase-n8.1.md) ✓ · ⧖ 2026-08-16
- **Depends on:** [sase-n8.8](sase-n8.8.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n8.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n8.9/README.md) | [sase-n8.9](sase-n8.9.md) | 0 |
