# Bead: sase-jx.5.1 — Repair the classifier's timestamp and per-run contract

[Bead Pages](../README.md) / [sase-jx.5](sase-jx.5.md) / sase-jx.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-jx.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.land/README.md) · **Assignee:** `sase-jx.5.1` · **Size:** medium
**Created:** 2026-08-12 12:14:23 EDT · **Closed:** 2026-08-12 12:30:06 EDT
**Plan:** [202608/land\_axe\_chop\_overrun.md](https://github.com/sase-org/sase--plans/blob/main/202608/land_axe_chop_overrun.md)

## Description

repair_core_contract: in sase-core, reject every run whose started_at is unparsable and extend the versioned verdict so Python can associate an overrun ratio with each raw cached run, then verify and publish the corrected binding without hand-editing release-plz-owned versions.

## Notes

[2026-08-12T16:30:06Z · sase-jx.5.1] Repaired the chop-overrun classifier's timestamp and per-run contract in sase-core (commit 46ce1fe, pushed to origin/master).

Fixed: sampled_blocking_ms now parses/validates started_at unconditionally for every otherwise-known-status run (completed/running/action) before deriving blocking_ms, instead of only for status=="running". A completed run with valid duration_ms but an unparsable started_at is now dropped as unsampled rather than classified off duration_ms alone; excluded statuses remain unaffected (already unsampled). Verified with a new test covering success/running/skipped/action_succeeded all given "not-a-timestamp".

Extended: ChopOverrunWire gained run_ratios: Vec<Option<f64>>, one entry per raw request.runs entry in order (None = unsampled, Some(ratio) = that run's own blocking/interval ratio). Existing summary fields (level, sampled_runs, over_runs, worst_ratio, worst_blocking_ms, latest_ratio) are unchanged. CHOP_OVERRUN_SCHEMA_VERSION bumped 1 -> 2 (no versioned shape changed under the old number). Verified with tests proving [skipped, over-success] -> run_ratios [None, Some(...)] with level="over" and latest_ratio pointing at the older sampled run, and a case locating an older overrun by raw index after a healthy newest run.

Updated PyO3 bindings in sase_core_py: round-trip test (chop_overrun_binding_returns_exact_plain_python_shape) now pins the 8-key shape including run_ratios; structural-error test's schema-mismatch fixture uses CHOP_OVERRUN_SCHEMA_VERSION + 1 instead of a stale hardcoded literal so it still asserts a real mismatch after the bump.

Verification: cargo fmt --all, then `just check` (fmt-check, clippy --workspace --all-targets -D warnings, cargo test --workspace including sase_core_py's abi3-py312 binding tests via the repo's PYO3_PYTHON resolution) — all green, exit 0. Did not hand-edit any Cargo version; release-plz owns publishing from master. sase-core working tree is clean and matches origin/master (46ce1fe).

## Dependencies

- **Blocks:** [sase-jx.5.2](sase-jx.5.2.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-jx.5.3](sase-jx.5.3.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jx.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jx.5.1/README.md) | [sase-jx.5.1](sase-jx.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@46ce1fe`](https://github.com/sase-org/sase-core/commit/46ce1fe9f1696f869007107114502b1b27f24bf6) | fix(axe\_overrun): validate started\_at unconditionally and align per-run ratios | [sase-jx.5.1](sase-jx.5.1.md) | 2026-08-12 12:29:09 EDT |
