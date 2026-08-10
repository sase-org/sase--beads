# Bead: sase-iy.4 — Fix the remaining contention-sensitive sase-ct nodes by mechanism

[Bead Pages](../README.md) / [sase-iy](README.md) / sase-iy.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xb](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xb/README.md) · **Assignee:** `sase-iy.4` · **Size:** medium
**Created:** 2026-08-10 11:02:04 EDT · **Closed:** 2026-08-10 12:39:29 EDT
**Plan:** [202608/retire\_sase\_ct\_umbrella.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_sase_ct_umbrella.md)

## Description

residue: take the non-visual nodes still recurring on sase-ct that waitgate does not already fix — agent-group revival, commits-pane filters, the vcs_tag pair, plugins-browser updates — and fix each by mechanism, using just test-contention as the falsifiable before/after harness.

## Notes

[2026-08-10T16:28:41Z · sase-iy.4] PROPOSED FOLLOW-UP: committed-plan validation rejects existing large tale plan sizes — just check-full failed before pytest on 21 pre-existing 202608 plans with tale-size-invalid; triage whether to convert them to epics, resize them, or adjust the validator migration path.

[2026-08-10T16:37:08Z · sase-iy.4] PROPOSED FOLLOW-UP: full test-cost has deterministic non-residue failures — just test-cost failed 3 nodes unrelated to this phase: stale tests/contract_manifest.txt now missing tests/test_sase_bead_tool.py, and large/xlarge tale follow-up model-selection tests expect @large_worker/@xlarge_worker while current behavior emits @medium_worker.

[2026-08-10T16:38:17Z · sase-iy.4] PROPOSED FOLLOW-UP: flake baseline gate still fails on historical post-baseline records — after the residue node set passed 0/3 locally, selection-health --fail-on-new-flake still reports seven durable-record nodes (glossary, agent-group, contract manifest, old cost-mode, VCS provider); retire/land should refresh or triage the historical gate once integrated verification is clean.

[2026-08-10T16:39:29Z · sase-iy.4] Implemented residue fixes: commits-pane filter test now waits for the exact status after authoritative reconciliation, and agent-group revival tests now use AcePage.wait_for instead of passing the page wrapper to the raw wait helper. Verified: focused commits node 1 passed, agent-group file 4 passed, and final residue soak just test-contention -- tests/test_agent_group_revival_e2e.py tests/ace/tui/test_commits_pane_filters.py tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py tests/ace/tui/test_plugins_browser_pane_sase_update_dev.py passed with 0 failed nodes across 3 repeats in 498.7s. Before fix: commits-pane failed 2/3; interim agent-group wrong-receiver failed 2/3 and 1/3. git diff --check clean. just check-full did not complete because unrelated committed-plan validation failed on 21 existing large tale plans; just test-cost and selection-health also failed on unrelated deterministic or historical-gate issues recorded as PROPOSED FOLLOW-UP notes.

[2026-08-10T16:41:00Z · sase-iy.4] Verified focused commits node passed, agent-group file passed, residue contention soak reported 0 node failures across 3 repeats, and git diff --check was clean; just check-full/test-cost/selection-health had unrelated pre-existing gate failures recorded as PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-iy.3](sase-iy.3.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-iy.5](sase-iy.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-iy.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-iy.4/README.md) | [sase-iy.4](sase-iy.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ebd3a91`](https://github.com/sase-org/sase/commit/ebd3a91bc16b3e1af6949177c2a475036af9f67a) | test: stabilize contention-sensitive TUI waits | [sase-iy.4](sase-iy.4.md) | 2026-08-10 12:41:54 EDT |
