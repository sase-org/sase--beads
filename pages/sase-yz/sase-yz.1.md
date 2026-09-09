# Bead: sase-yz.1 — Collector health domain model in the Rust core

[Bead Pages](../README.md) / [sase-yz](README.md) / sase-yz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hd.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hd.f1.md) · **Assignee:** `sase-yz.1` · **Size:** medium
**Created:** 2026-09-09 12:39:15 EDT · **Closed:** 2026-09-09 14:21:35 EDT
**Plan:** [202609/usage\_collector\_health\_and\_drift\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collector_health_and_drift_resilience.md)

## Description

health-core: track failure-streak start in the refresh schedule, project a per-provider collector_health block into the public snapshot, gate and re-rank CollectionProblem attention on consistent failure, add the vendor_drift reason code, and coordinate the sase-core release plus the sase-side floor bump.

## Notes

[2026-09-09T18:20:25Z · sase-yz.1] PROPOSED FOLLOW-UP: Raise the sase-core-rs floor after the collector-health core release - the currently published 0.32.56 wheel was checked and does not expose vendor_drift or provider_usage_collector_failing_threshold, so pyproject.toml/uv.lock must wait for the release containing this phase.

[2026-09-09T18:20:56Z · sase-yz.1] PROPOSED FOLLOW-UP: Triage intermittent main just-check flakes - full-suite runs failed once each in tests/dispatch/test_machine_bootstrap_real_gateway.py::test_bootstrap_issue_enroll_hello_round_trip_through_real_gateway and tests/llm_provider/test_usage_transport.py::test_jsonline_descendant_cleanup, and both passed on exact rerun; final just check passed.

[2026-09-09T18:21:35Z · sase-yz.1] Implemented collector health in sase-core: first_failure_at streak tracking, collector_health snapshot projection, vendor_drift reason code, CollectionProblem gating/rank order, PyO3 threshold binding, and Python reason-code coverage. Verified cargo test -p sase_core provider_usage -- --nocapture; PYO3_PYTHON=/usr/bin/python3 cargo test -p sase_core_py provider_usage -- --nocapture; PYO3_PYTHON=/usr/bin/python3 just check in sase-core; just rust-dev-install; main just check; focused usage_config pytest; live usage list JSON includes collector_health keys. Published 0.32.56 lacks this contract, so floor bump is release-gated and noted.

## Dependencies

- **Blocks:** [sase-yz.2](sase-yz.2.md) ◐ · ⧖ 2026-09-09
- **Blocks:** [sase-yz.3](sase-yz.3.md) ◐ · ⧖ 2026-09-09
- **Blocks:** [sase-yz.4](sase-yz.4.md) ◐ · ⧖ 2026-09-09
- **Blocks:** [sase-yz.5](sase-yz.5.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yz.1/README.md) | [sase-yz.1](sase-yz.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a4fb21`](https://github.com/sase-org/sase/commit/7a4fb2149a1d308299d968f0f3d7c477c72dbaec) | feat(usage): accept vendor drift reason | [sase-yz.1](sase-yz.1.md) | 2026-09-09 14:23:37 EDT |
| sase-core | [`sase-core@fcd4b4e`](https://github.com/sase-org/sase-core/commit/fcd4b4e9b955e6c2073b663712627ca5433eaad5) | feat(provider-usage): expose collector health | [sase-yz.1](sase-yz.1.md) | 2026-09-09 14:26:58 EDT |
