# Bead: sase-1ko.4 — Handoff-aware declaration and memory-read readout, with the pre-cutover baseline attached

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.4` · **Size:** medium
**Created:** 2026-10-13 18:10:35 EDT · **Closed:** 2026-10-13 22:15:07 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

readout: add `sase instructions readout`. Per provider and delivery mode, it classifies finished root runs as accepted, plan handoff, monitor handoff, not required, or miss, and joins memory reads per run. Reproduce the planning-time baseline, and attach the pre-cutover baseline JSON to the epic.

## Notes

[2026-10-14T02:14:43Z · sase-1ko.4] PROPOSED FOLLOW-UP: symvision flags pre-existing private imports _RunManifest (show.py) and _render_sections_table (show.py from instructions_handler) — files untouched by readout phase, `sase tool run check` otherwise green on fmt/ruff/mypy; triage as e3-readout follow-up

[2026-10-14T02:14:55Z · sase-1ko.4] Baseline readout: Sep10-Oct5 totals match (claude 235/233, codex 243/236, grok 158/158, muse 526/525); misses claude 1 vs 6, codex 4 vs 8, grok 12 vs 22, muse 28 vs 40. Oct6-Oct13 totals match (claude 80/72, codex 129/123, grok 82/80, muse 244/245); misses 1 vs <=2, 0 vs <=3, 6 vs <=4, 12 vs <=22. Gaps from stricter handoff detection (plan validate, real-prepare vs help, --mon/--gate suffix families) and upper-bound baselines; memory grok/codex/muse match, claude 2.39 vs 1.71 from artifacts_dir-exact join. JSONs attached as e3_readout_baseline_*.json.

[2026-10-14T02:15:07Z · sase-1ko.4] Implemented sase instructions readout (per provider x mode, 8 classes, memory join, schema_version 1); parser/handler/docs/completion updated; 15 new readout tests plus 52 related tests pass; baselines attached as e3_readout_baseline_*.json; epic-symbols empty

[2026-10-14T02:37:45Z · sase-1ko.4] Restored sase instructions readout after workspace reset: per provider x mode, 8 classes, memory join, schema_version 1; parser/handler/docs/completion snapshot; 15 readout tests plus 383 related tests pass; baselines already on epic; epic-symbols empty

[2026-10-14T03:56:23Z · sase-1ko.4--1] Recovery after 1h just check timeout: made RunManifest and render_sections_table public (show.py cross-file imports) and privatized same-file readout/show helpers so symvision is clean; 15 readout tests plus just _lint-symvision pass. Re-running just check for host completion.

## Dependencies

- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.3](sase-1ko.3.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.4.md) | [sase-1ko.4](sase-1ko.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e79a89d`](https://github.com/sase-org/sase/commit/e79a89d755a1f91cb032bd2199709994ab9d5d9d) | feat(instructions): add handoff-aware declaration readout | [sase-1ko.4](sase-1ko.4.md) | 2026-10-14 00:20:55 EDT |
