# Bead: sase-ib.4 — Cut cross-cutting per-test overhead outside the TUI

[Bead Pages](../README.md) / [sase-ib](README.md) / sase-ib.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wk/README.md) · **Assignee:** `sase-ib.4` · **Size:** medium
**Created:** 2026-08-09 10:31:57 EDT · **Closed:** 2026-08-09 12:24:55 EDT
**Plan:** [202608/fast\_test\_suite\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_test_suite_1.md)

## Description

overhead: remove the repeated full-argparse parser builds, gettext lookups, YAML/config reparses, and avoidable CLI subprocess round-trips that the harness attributes across the non-TUI suite.

## Notes

[2026-08-09T16:24:30Z · sase-ib.4] PROPOSED FOLLOW-UP: Split subprocess cost attribution - the subprocess.run bucket mixes deliberate git/nested-pytest/generated-gate/process-boundary tests with avoidable CLI round-trips, making this phase metric too coarse to use directly.

[2026-08-09T16:24:55Z · sase-ib.4] Verified just check passed with full-suite escalation; targeted parser/config cost run passed 72 tests with parser 4.770s->0.077s, gettext 48753 probes->21, YAML 0.361s->0.176s; full cost run passed 28023 tests across 28032 nodes before the final hot-file parser rewrite with YAML 65s->13.257s, parser 60s->41.987s, gettext 22 probes; focused current-tree hot parser run passed 198 tests with parser 2.724s/264 parses and no node drop.

[2026-08-09T16:26:09Z · sase-ib.4] Verified just check passed with full-suite escalation; full cost run passed 28023 tests across 28032 nodes; targeted parser/config and hot parser cost samples showed parser/gettext/YAML overhead reductions.

## Dependencies

- **Depends on:** [sase-ib.1](sase-ib.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ib.7](sase-ib.7.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ib.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ib.4/README.md) | [sase-ib.4](sase-ib.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`98d9584`](https://github.com/sase-org/sase/commit/98d95848a6d7a8e278ab0686a51aaa9d74c65eb1) | perf: reduce repeated non-TUI test overhead | [sase-ib.4](sase-ib.4.md) | 2026-08-09 12:27:30 EDT |
