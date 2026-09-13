# Bead: sase-zu.8.2 — Make indexed history authoritative without archive-wide marker repair

[Bead Pages](../README.md) / [sase-zu.8](sase-zu.8.md) / sase-zu.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.2` · **Size:** medium
**Created:** 2026-09-13 10:21:15 EDT · **Closed:** 2026-09-13 12:39:44 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

index-freshness: repair the Rust-owned completeness and discovery contract, bound steady-state revalidation, and adopt its wire through the existing Python loader.

## Notes

[2026-09-13T16:39:44Z · sase-zu.8.2] Repaired Rust-owned index completeness: revalidate+full-history now discovers previously unindexed directories and drops deleted ones instead of serving stale record_json, then stamps a source-reconcile watermark. Cached full-history claims complete_history only when that watermark is still valid. Marker revalidation no longer pre-scans every where_sql row before candidate filtering (Tier 1 revalidate is bounded to the selected cap plus hidden-row repair). Python query_artifact_index_for_loader adopts snapshot.index_completeness instead of treating include_full_history as proof of completeness; overflow invalidates the watermark.

Verified: sase-core clippy/fmt pass; new index tests cover discovery, deletion, hidden toggle, watermark reuse, and bounded Tier 1 candidate revalidate; agent_scan_parity 45/45; sase_core_py 144 passed / 2 ignored. Python focused oracle/loader/wire tests 33/33, including post-build discovery, deleted-row drop, hidden repair, and cached-after-settle zero marker work. just check lint gates (ruff/mypy/fmt/feature-flags/pyscripts/test-waits/changelog/terminology/symvision/toobig) pass. just check's scoped lane escalated to the full suite (core-identity-changed): 41303 passed; the 11 failures are the pre-existing missing continuation_decide_resume_adoption binding recorded on sase-zu.8.1, unrelated to this phase. sase bead epic-symbols sase-zu.8.2 reports no entries.

## Dependencies

- **Depends on:** [sase-zu.8.1](sase-zu.8.1.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zu.8.3](sase-zu.8.3.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.8.2/README.md) | [sase-zu.8.2](sase-zu.8.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5beda06`](https://github.com/sase-org/sase/commit/5beda061fc5e3ac8e9c6954ba5e7398ff00129ce) | fix(ace): adopt rust index completeness for full-history loads | [sase-zu.8.2](sase-zu.8.2.md) | 2026-09-13 12:42:05 EDT |
| sase-core | [`sase-core@1b12228`](https://github.com/sase-org/sase-core/commit/1b12228757318afbd7b4b2061e7303e153d75524) | fix(agent-scan): discover source dirs before claiming complete history | [sase-zu.8.2](sase-zu.8.2.md) | 2026-09-13 12:44:08 EDT |
