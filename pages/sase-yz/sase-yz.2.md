# Bead: sase-yz.2 — Drift-classifying probe strategies for all collectors

[Bead Pages](../README.md) / [sase-yz](README.md) / sase-yz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hd.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hd.f1.md) · **Assignee:** `sase-yz.2` · **Size:** medium
**Created:** 2026-09-09 12:39:15 EDT · **Closed:** 2026-09-09 20:02:26 EDT
**Plan:** [202609/usage\_collector\_health\_and\_drift\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collector_health_and_drift_resilience.md)

## Description

drift-probes: add a shared bounded probe-strategy runner with drift classification, adopt it in the Claude, Codex, and Grok collectors, annotate fallback recoveries on ok observations, and extend the live-mirroring fixtures to cover strategy chains and drift classification.

## Notes

[2026-09-09T21:43:08Z · sase-yz.2--4] PROPOSED FOLLOW-UP: Investigate pager copy-label action flake - tests/pager/test_app_actions.py::test_y_then_label_copies_the_links_resolved_path is now the sole selection-health --fail-on-new-flake blocker; it passed focused in this workspace and appears unrelated to usage collector drift-probe changes.

[2026-09-09T23:59:37Z · sase-yz.2--5] PROPOSED FOLLOW-UP: Revisit test-cost hard budgets after latest calibration - check-full monitor 544spgexwjpz passed all lint/validation and 40072 tests, 14 skipped, then failed only the test-cost budget gate with total_file_cpu_seconds 3186.381 > 3000 tolerated and textual_app_run_test_enter.cpu 868.497 > 862.500 tolerated; duplicate evidence recorded on existing task sase-xc and unrelated to usage collector drift-probe changes.

[2026-09-10T00:02:26Z · sase-yz.2--5] Verified targeted drift-probe suites (59 passed), standalone symvision, selection-health --fail-on-new-flake, final epic-symbols check, and live run_usage_probe smoke for claude/codex/grok (ok: 3/3/1 windows). Monitored check-full 544spgexwjpz passed all lint/validation and 40072 tests, then failed only the known test-cost hard-budget regression; recorded duplicate evidence on reopened task sase-xc and a PROPOSED FOLLOW-UP note here. Also re-keyed stale artifact-link symvision epic-symbols from closed sase-yy.4/sase-yy.5 to open sase-yy.6.

## Dependencies

- **Depends on:** [sase-yz.1](sase-yz.1.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yz.5](sase-yz.5.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yz.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yz.2.md) | [sase-yz.2](sase-yz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`afc5226`](https://github.com/sase-org/sase/commit/afc52262f4dcaa9b4144c772c8795b3373870230) | feat(usage): add drift-classifying probe strategies | [sase-yz.2](sase-yz.2.md) | 2026-09-09 20:32:47 EDT |
