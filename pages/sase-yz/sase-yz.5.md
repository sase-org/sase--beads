# Bead: sase-yz.5 — Integrated verification, live smoke, and docs

[Bead Pages](../README.md) / [sase-yz](README.md) / sase-yz.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hd.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hd.f1.md) · **Assignee:** `sase-yz.5` · **Size:** small
**Created:** 2026-09-09 12:39:18 EDT · **Closed:** 2026-09-10 05:21:36 EDT
**Plan:** [202609/usage\_collector\_health\_and\_drift\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collector_health_and_drift_resilience.md)

## Description

health-verify: run the combined acceptance checks including check-full through a monitor, perform a bounded live smoke plus an induced-failure walkthrough on an isolated SASE_HOME, and document collector health and the indicator.

## Notes

[2026-09-10T06:39:30Z · sase-yz.5--3] PROPOSED FOLLOW-UP: triage selection-health baseline debt for five promoted dirty-tree nodes — check-full selection-health promoted three batch-predecessor metadata nodes plus dev-extension binding and directive-contract nodes; all five passed focused on this tree, and the baseline stanza was added so this phase can land while a land/task owner decides whether to file or retire the debt.

[2026-09-10T08:44:10Z · sase-yz.5--4] PROPOSED FOLLOW-UP: suite test-cost hard CPU budgets needed another athena-only raise during landing — check-full passed 40141 tests then failed total_file_cpu_seconds 3066.482 vs 3000 allowance; standing stale-budget work remains on sase-xc

[2026-09-10T09:21:36Z · sase-yz.5--5] verified targeted regression pytest; selection-health passed; just check passed; just check-full passed; live usage smoke and induced Codex vendor-drift walkthrough completed

## Dependencies

- **Depends on:** [sase-yz.1](sase-yz.1.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-yz.2](sase-yz.2.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-yz.3](sase-yz.3.md) ✓ · ⧖ 2026-09-09
- **Depends on:** [sase-yz.4](sase-yz.4.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yz.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yz.5.md) | [sase-yz.5](sase-yz.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5aef515`](https://github.com/sase-org/sase/commit/5aef515e688e98736a9a0417e39fb28923a9aa28) | docs(usage): document collector health and land health-verify | [sase-yz.5](sase-yz.5.md) | 2026-09-10 05:23:57 EDT |
