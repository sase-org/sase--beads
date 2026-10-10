# Bead: sase-1jc.6 — Remove the legacy live Agents query implementation

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.6` · **Size:** medium
**Created:** 2026-10-09 22:28:25 EDT · **Closed:** 2026-10-10 08:23:15 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

agents-query: Follow phase 6 and the shared removal checklist. Retire agents_unified_query and close sase-zg. Make the Rust agents-live profile and FilterBar unconditional. Delete the legacy live parser/evaluator, QueryEditModal, and dependent dead state after checking every consumer. Preserve current saved-query compatibility, history scoping, Rust pushdown, and asynchronous refresh performance. Verify behavior and affected visual fixtures.

## Notes

[2026-10-10T12:22:56Z · sase-1jc.6] PROPOSED FOLLOW-UP: symvision NEW finding ArtifactIndexProjection in src/sase/agents/catalog/_sources.py reproduces identically on the clean base tree (verified via stash plus direct symvision run); pre-existing and unrelated to the agents-query retirement

[2026-10-10T12:23:00Z · sase-1jc.6] PROPOSED FOLLOW-UP: per epic plan decision macro_memory=no, update sase/memory/macros.md to describe typed Proc launches as unconditional

[2026-10-10T12:23:05Z · sase-1jc.6] PROPOSED FOLLOW-UP: per epic plan decision refresh_memory=no, update sase/memory/tui_perf.md rule 14 to describe refresh tokens as unconditional

[2026-10-10T12:23:15Z · sase-1jc.6] Retired agents_unified_query (closed sase-zg): removed registry definition and config row, regenerated schema; Rust agents-live profile and FilterBar unconditional; deleted legacy agent_query package (parser/evaluator/pushdown/tokenizer/types/highlighting), QueryEditModal plus exports/styles, and Off branches across loader/compute/finalize/filter/prospective/help/machines/seed/jump/history paths; preserved saved-query legacy-dialect warning compatibility, live history keys, Rust pushdown, and async refresh. Verified: just fmt clean; repo ruff and mypy clean; feature-flags lint green after sase-zg close; focused suites green (persistence, unified filter, pushdown, loader window, finalize plan/fleet, seed, machines, node jump/finder, refresh, kill/dismiss, completion, filter-bar, tiering oracle, timezone, macro directives, conformance); targeted visual capture clean (16 goldens unchanged). Pre-existing symvision ArtifactIndexProjection fails identically on base (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-1jc.5](sase-1jc.5.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.7](sase-1jc.7.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.6/README.md) | [sase-1jc.6](sase-1jc.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b46ecb0`](https://github.com/sase-org/sase/commit/b46ecb0a947539855d69034bd4d1300b999274af) | feat(agents): retire agents\_unified\_query flag, unify live query path | [sase-1jc.6](sase-1jc.6.md) | 2026-10-10 08:26:04 EDT |
