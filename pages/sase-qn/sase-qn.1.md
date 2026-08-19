# Bead: sase-qn.1 — Large-catalog bench harness and recorded baselines

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.1` · **Size:** small
**Created:** 2026-08-18 20:12:38 EDT · **Closed:** 2026-08-18 20:45:55 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

bench: add a slow-marked scale bench and large synthetic catalog fixture for the Updates > Plugins sub-tab, record p50/p95/max baselines at 10/250/1000/2000 entries, and assert the fetch/enrich cost curves so later phases have a measuring stick.

## Notes

[2026-08-19T00:44:58Z · sase-qn.1] Recorded baselines in tests/perf/baselines/plugin_catalog_scale_baseline.json. Enrich is n^2: n=1000 p50=317ms scan_work=1e6; n=2000 p50=1260ms scan_work=4e6; fetch pages 1/3/10/20. TUI filter (fixed 100 matches) p95 0.4/3.0/4.5/11.0 ms; j p95 stays <1 ms; jump-hint rebuild of the unfiltered list is the TUI path over 16 ms (p95 31 ms at n=1000, 63 ms at n=2000). Budgets recorded, not enforced.

[2026-08-19T00:45:15Z · sase-qn.1] PROPOSED FOLLOW-UP: flag bead tests fail on this tree — sase-core-rs wire rejects issue_type=flag (unknown variant; sqlite has no flag column). just check escalated to the full suite after the Justfile recipe and failed 16 flag-bead tests; core-floor-probe already reports blocked_unpublished. Not caused by this phase.

[2026-08-19T00:45:31Z · sase-qn.1] PROPOSED FOLLOW-UP: test_ace_page_fast_startup_is_structurally_quiet left a cancelled pump-free task sase-artifacts-project-choices. Unrelated to the Plugins scale bench; did not touch AcePage startup.

[2026-08-19T00:45:55Z · sase-qn.1] Added slow scale benches plus a committed measuring-stick baseline at 10/250/1000/2000. Verified enrich scan_work is n^2 (1e6 -> 4e6) with one fetch per entry, fetch page counts 1/3/10/20, and TUI filter match count stays 100 (10 at n=10). Recorded p50/p95/max; budgets not enforced. Fast structural tests passed; slow TUI and enrich/fetch benches passed. just check lint gates passed; scoped tests escalated (Justfile) and 17 failures were pre-existing flag-bead/core-floor plus an unrelated AcePage leftover-task assert.

[2026-08-19T00:47:29Z · sase-qn.1] Plugins catalog scale harness at 10/250/1000/2000 with committed baseline tests/perf/baselines/plugin_catalog_scale_baseline.json; wall-clock budgets recorded not enforced. Fast structural tests passed (6). Slow TUI + enrich/fetch benches passed. Filter match count held at 100 (10 at n=10). just bench-plugin-catalog-scale recipe added. epic-symbols: no leftovers.

## Dependencies

- **Blocks:** [sase-qn.2](sase-qn.2.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.3](sase-qn.3.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.4](sase-qn.4.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-qn.5](sase-qn.5.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.1/README.md) | [sase-qn.1](sase-qn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`42a8193`](https://github.com/sase-org/sase/commit/42a81937b9dedd61eb8a77b3d691565e793acb0e) | test(perf): add plugins catalog scale bench harness | [sase-qn.1](sase-qn.1.md) | 2026-08-18 20:52:44 EDT |
