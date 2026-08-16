# Bead: sase-m6.7.1.3 — One host-owned relation panel and generalized jumpers

[Bead Pages](../README.md) / [sase-m6.7.1](sase-m6.7.1.md) / sase-m6.7.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.3` · **Size:** large
**Created:** 2026-08-16 02:53:31 EDT · **Closed:** 2026-08-16 06:55:05 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Description

panel: replace AncestorsChildrenPanel with a shell-owned RelationPanel, generalize the ancestor/child/sibling key modes off Patch onto any pane with the RELATIONS capability, and route cross-pane edges through the shared entry request.

## Notes

[2026-08-16T09:52:59Z · sase-m6.7.1.3] PERF VERIFICATION (2026-08-16): .venv/bin/pytest -s -m slow tests/ace/tui/bench_tui_jk.py::test_bench_patches_jk passed; Patches p95 stitches.next=2.45 ms, stitches.prev=1.51 ms. .venv/bin/pytest -s -m slow tests/ace/tui/bench_artifacts_jk.py passed; all Artifacts p95 values <16 ms: next=6.43, prev=7.62, stitches.next=10.50, stitches.prev=10.48, beads.next=1.72, beads.prev=5.31, ref:plan.next=1.07, ref:plan.prev=1.06, files.next=5.25, files.prev=4.98, stitches.first=1.50, stitches.last=1.36, stitches.down10=1.56, stitches.up10=11.30, beads.first=1.93, beads.last=1.56, beads.down10=1.48, beads.up10=12.99, ref:plan.first=0.75, ref:plan.last=0.62, ref:plan.down10=0.54, ref:plan.up10=0.58, files.first=1.25, files.last=1.30, files.down10=1.44, files.up10=7.67. Diff grep confirmed build_relation_index/build_*_relation_index calls remain in relation builders, snapshot loader paths, and tests; no relation builder call was added to the keystroke/panel path.

[2026-08-16T10:55:05Z · sase-m6.7.1.3] Implemented generic artifact relation panel and relation jumpers. Verified: just fmt; focused relation/navigation/regression suite passed; selected Artifacts/Patch visual snapshots passed with scoped golden updates; Patch and Artifacts j/k perf benches stayed under the 16 ms p95 budget; just check passed, including full non-slow non-visual pytest escalation. just check-full was not completed because sase monitor could not attach to this agent.

[2026-08-16T11:37:33Z · sase-m6.7.1.3--3] Relation panel + generalized jumpers verified: just check passed; just check-full passed every lint gate (fmt, keep-sorted, ruff, mypy, symvision, toobig, sase validation) with 30960 passed / 11 skipped and only the already-tracked process-global config-cache flake sase-mv failing (3 tests, none with a changed file in their import graph). Perf gate recorded: Patches p95 2.45/1.51 ms, every Artifacts pane p95 under the 16 ms budget (max 12.99 ms). Also restored two files that this phase's commit a0b6cd16b reverted during its rebase: tests/test_agent_artifact_directory_operation_audit.py (duplicate dict key, ruff F601, broke every commit repo-wide via commit_hooks.before) and tests/workspace_provider/test_workspace_lease.py (10 NameError failures); both are back to their 71012c5c7 content and pass (20 passed).

## Dependencies

- **Depends on:** [sase-m6.7.1.2](sase-m6.7.1.2.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-m6.7.1.4](sase-m6.7.1.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.1.3.md) | [sase-m6.7.1.3](sase-m6.7.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0b6cd1`](https://github.com/sase-org/sase/commit/a0b6cd16bafc0cf4b4c17d760ebdc47e38875f8c) | feat(tui): generalize artifact relation navigation | [sase-m6.7.1.3](sase-m6.7.1.3.md) | 2026-08-16 06:58:13 EDT |
| sase | [`467f8c1`](https://github.com/sase-org/sase/commit/467f8c184e08967805b3faf74ba1995c3307966a) | test: restore two test files reverted by a0b6cd16b | [sase-m6.7.1.3](sase-m6.7.1.3.md) | 2026-08-16 07:38:51 EDT |
