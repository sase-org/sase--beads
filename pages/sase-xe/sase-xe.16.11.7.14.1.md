# Bead: sase-xe.16.11.7.14.1 — Owner-side presentable snapshot scope and honest freshness

[Bead Pages](../README.md) / [sase-xe.16.11.7.14](sase-xe.16.11.7.14.md) / sase-xe.16.11.7.14.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0it](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0it.md) · **Assignee:** `sase-xe.16.11.7.14.1` · **Size:** large
**Created:** 2026-09-10 13:39:03 EDT · **Closed:** 2026-09-10 14:45:59 EDT
**Plan:** [202609/fleet\_stale\_remote\_rows.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_stale_remote_rows.md)

## Description

owner-scope: apply a core-owned presentable policy to the gateway fleet snapshot (demote dead active-tier records, bound recent completions, fold or drop orphaned members of dismissed families), replace hard-coded Fresh stamps with age-derived freshness plus an age-based snapshot rebuild, and make status bucketing liveness-aware.

## Notes

[2026-09-10T18:45:59Z · sase-xe.16.11.7.14.1] Implemented in sase-core (sibling repo):
- New core-owned fleet_presentation policy (crates/sase_core/src/fleet_presentation.rs): decides current vs recent-terminal vs excluded per candidate, merging genuinely-terminal and demoted Dead/NotProcess active-tier records under one combined 200-row/7-day bound, never demoting Alive/Unknown or waiting/question-protected rows.
- New bounded core index API resolve_family_dismissal_lineage (agent_scan/index.rs) that walks parent_timestamp/retry lineage (bounded, reusing the existing query_related_agent_artifact_dirs machinery) to find a candidate's family root and check it against dismissed_agents.
- fleet_contract.rs: liveness-aware status bucketing (bucket_for_lifecycle now takes liveness; Dead/NotProcess + Running/Starting/Unknown -> Stopped), counts_as_running requires compatible liveness directly, and a new family_role (root/member/monitor/gate/proc/historical_shell) + parent_timestamp on ResolvedAgentSummaryWire for later viewer folding, with a new consistency invariant in validate_resolved_agent_summary.
- crates/sase_gateway/src/fleet_reads.rs: build_snapshot_blocking now resolves liveness once per candidate, obtains dismissal-lineage facts, runs the presentation policy, and only projects the selected set; demoted rows lose current_instance/action capabilities. Row/envelope freshness is now derived from one build instant via classify_cache_freshness (fresh <5s, aging <60s, stale/rebuild-required >=60s) instead of a hard-coded Fresh stamp; a stale cache forces a rebuild attempt, concurrent rebuilds still coalesce under the existing refresh_lock, and a failed/timed-out rebuild still retains the previous snapshot marked stale/partial.
- Updated crates/sase_gateway/contracts/api_fleet_v1/fleet_api_v1.json (regenerated via UPDATE_FLEET_CONTRACT=1) for the new ResolvedAgentSummaryWire fields.

Verified: ./scripts/check.sh all (fmt-check, clippy --workspace --all-targets -D warnings, cargo test --workspace including sase_core_py PyO3 bindings and doc-tests) is fully green with LD_LIBRARY_PATH pointed at the uv-managed python3.14 shared lib. sase bead epic-symbols sase-xe.16.11.7.14.1 reports no entries.

Behavioral cases covered by new tests: live/unknown candidates always stay current; a waiting/question-protected record stays current even if liveness is Dead; a Dead/NotProcess active-tier record demotes into the shared recent-terminal window; genuinely-terminal and demoted records share one combined 200-row/7-day bound (window and cap both tested); dead orphans of a dismissed family are excluded while live members of a dismissed family are never excluded; family_role distinguishes root/member/historical-shell and status_bucket is liveness-aware at the projection layer; counts_as_running requires compatible liveness independent of current_instance; resolve_family_dismissal_lineage follows parent_timestamp to a dismissed root and never treats an out-of-index parent pointer as dismissed; at the gateway level, a dead-active leftover is demoted+served while one outside the 7-day window is excluded, a dead orphan of a dismissed family disappears from the catalog entirely, an aged cache triggers exactly one coalesced rebuild across concurrent readers, and a failed rebuild retains the previous snapshot marked stale/partial without incrementing the refresh count.

PROPOSED FOLLOW-UP: scripts/check.sh's PYO3_PYTHON auto-selection finds a qualifying python3.14 interpreter but the sase_core_py test binary then fails at runtime with "error while loading shared libraries: libpython3.14.so.1.0" unless LD_LIBRARY_PATH also points at that interpreter's lib dir; check.sh does not set this today, so a fresh machine hits an opaque exit-127 failure on `test`/`all` (fmt-check and clippy still pass since they do not execute the pyo3 binary). Worth having check.sh derive and export LD_LIBRARY_PATH alongside PYO3_PYTHON.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.14.3](sase-xe.16.11.7.14.3.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.1.md) | [sase-xe.16.11.7.14.1](sase-xe.16.11.7.14.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@270e501`](https://github.com/sase-org/sase-core/commit/270e50168391d38a32083f12ebac5afda0a8247d) | feat(fleet): bound owner-side presentation and derive honest freshness | [sase-xe.16.11.7.14.1](sase-xe.16.11.7.14.1.md) | 2026-09-10 14:47:06 EDT |
