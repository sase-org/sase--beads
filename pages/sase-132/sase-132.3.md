# Bead: sase-132.3 — Cut the bounded Tier 1 load's absolute cost

[Bead Pages](../README.md) / [sase-132](README.md) / sase-132.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0n7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0n7.md) · **Assignee:** `sase-132.3` · **Size:** large
**Created:** 2026-09-18 15:22:35 EDT · **Closed:** 2026-09-18 18:03:35 EDT
**Plan:** [202609/tui\_startup\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202609/tui_startup_regression.md)

## Description

loader-diet: attribute and reverse the standalone bounded-load creep (production_bounded p50 1002 ms on 2026-09-13 to 1632 ms on 2026-09-18 at +3% archive growth), including the ~11x decode amplification (about 1,062 records decoded to return 96 rows) and index row growth, with Rust-core pushdown evaluated under the rust_core_backend_boundary rule.

## Notes

[2026-09-18T22:02:31Z · sase-132.3] PROPOSED FOLLOW-UP: old waiting/question marker-only ace-run rows remain SQL-active in the artifact index even after Agents-list projection skips their JSON hydration. A durable index retention/vacuum policy for those rows is out of scope for sase-132.3 and still belongs to a later compaction/retention task, not a Python-side filter.

[2026-09-18T22:03:35Z · sase-132.3] Implemented Agents-list projection (default-off `agents_list_projection`) in sase-core and enabled it only on the TUI tiered loader query.

Rust: scalar/index-side projectable predicate before `record_json` hydration (done+supported workflow dir, home ace-run+running marker, workflow-state loader dirs). Clan keys/context for waiting-only records come from indexed scalar columns. Generic index callers unchanged. sase bead epic-symbols sase-132.3: no remaining --epic-symbol entries.

Checks:
- sase-core `just check` equivalent: fmt, clippy -D warnings, `cargo test --workspace` passed (index projection tests + agent_scan_parity + gateway fleet_reads).
- Python focused: wire, loader-window, projection parity (done/home-running/workflow/waiting-only/noop/hidden/family/running-claim clan), production oracle, bench smoke (3.0x assertion) passed.
- just check on sase: fmt/ruff/mypy/pyscripts/validate passed. Pre-existing on HEAD: Symvision unused public ArtifactFileCache, MultiPrompt, TailCache (reproduced on clean tree). test-scoped escalated (core-identity-changed) to full suite: 43173 passed; 16 failed were unrelated sdd sidecar clone HEAD / fish-loader / modal-cancel flakes, not loader-diet.

Synthetic 1500-artifact fixture (`not machine:apollo`, limit 100): production_bounded p50 56.9 ms, decoded 102 / 99 visible = 1.03x, loaded_row_count 100; production_full_history missing_count=0.

Busy-host athena real archive (11884 artifacts, load 27.92 34.04 33.49 on 64 nproc, working tree + rebuilt sase_core_rs from dirty sase-core): production_bounded p50 1127 ms (27 ms over the 1.1 s quiet-host target), decoded 259 for 64 visible on `not machine:apollo`; production_full_history missing_count=0. Quiet-host capture was not obtainable; target unchanged.

PROPOSED FOLLOW-UP already noted: index retention/vacuum for SQL-active marker-only waiting/question rows.

## Dependencies

- **Depends on:** [sase-132.1](sase-132.1.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-132.7](sase-132.7.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-132.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-132.3.md) | [sase-132.3](sase-132.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13a8efb`](https://github.com/sase-org/sase/commit/13a8efbb4ad4adc7a1694238b27a2613cf78553f) | feat(tui): project Agents-list index rows before JSON hydration | [sase-132.3](sase-132.3.md) | 2026-09-18 18:06:08 EDT |
| sase-core | [`sase-core@8e1b8b6`](https://github.com/sase-org/sase-core/commit/8e1b8b6e0b9389862bc48dea0099030578d638c6) | feat(agent-scan): add default-off Agents-list projection mode | [sase-132.3](sase-132.3.md) | 2026-09-18 18:24:54 EDT |
