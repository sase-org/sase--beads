# Bead: sase-z4.6.5.4.6.2 — Repair the research package compatibility contract

[Bead Pages](../README.md) / [sase-z4.6.5.4.6](sase-z4.6.5.4.6.md) / sase-z4.6.5.4.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.5.4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.4.land.md) · **Assignee:** `sase-z4.6.5.4.6.2` · **Size:** medium
**Created:** 2026-09-12 06:29:17 EDT · **Closed:** 2026-09-13 18:51:50 EDT
**Plan:** [202609/weighted\_capacity\_lifecycle\_and\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_lifecycle_and_release.md)

## Description

package-contract: reconcile the research plugin's incompatible core window and stale wheel assertions with the actual containing release and the current SASE API requirements.

## Notes

[2026-09-13T19:50:19Z · sase-z4.6.5.4.6.2] Aligned the research plugin compatibility contract with the current SASE/core cohort.

Current published index: sase 0.17.1 (core window >=0.32.16,<0.33.0), sase-core-rs 0.34.24, sase-research-artifacts 0.2.0. SASE source at this workspace requires sase-core-rs>=0.34.23,<0.35.0 and is still versioned 0.17.1; 0.17.2 is the unreleased containing host (open release PR #299). Plugin source at 5aaa244 required sase>=0.17.2 and the disjoint sase-core-rs>=0.33.0,<0.34.0, which is the CI failure on research release PR #2 run 34664698929.

Changes in the opened sase-research-artifacts checkout:
- pyproject core window is now sase-core-rs>=0.34.23,<0.35.0, matching current SASE.
- Wheel metadata, source-coordination smoke (0.34.* + policy schema >= 4), and published-minimum exact pins (sase==0.17.2, sase-core-rs==0.34.23) follow that cohort.
- Published-minimum stays wheel-only (no overrides/maturin) and now also refuses sase==0.17.1 and sase-core-rs==0.33.0.
- Expansion tests assert canonical queue_capacity (and the wait_runners alias) and that emitted %q(...) uses capacity= rather than runners=.
- A runtime intersection test checks the plugin core window accepts the installed SASE floor.

Did not ratchet SASE's own floor (already 0.34.23) and did not hand-edit release-please-owned plugin version 0.2.0. Published 0.17.2 still does not exist; establishing that release is published-proof (sase-z4.6.5.4.6.3), not this phase.

[2026-09-13T22:51:50Z · sase-z4.6.5.4.6.2--2] Verified package-contract on the opened sase-research-artifacts checkout: pyproject core window is sase-core-rs>=0.34.23,<0.35.0 matching current SASE, with sase>=0.17.2 kept as the containing host floor. just check passed (ruff, mypy, 48 pytest). just test-wheel passed (4 source-coordination wheel tests). Expansion tests assert canonical queue_capacity (wait_runners alias), emitted %q uses capacity= not runners=, explicit runners=0 still renders capacity=0 on all four segments and extract_prompt_directives raises DirectiveError matching 'at least 1', and runners=1 / priority=0 still parse. Published-minimum stays wheel-only with exact pins sase==0.17.2 and sase-core-rs==0.34.23, and refuses sase==0.17.1 and sase-core-rs==0.33.0. Runtime intersection test accepts the installed SASE core floor. No leftover --epic-symbol entries. Did not ratchet SASE's floor or hand-edit plugin version 0.2.0; establishing published 0.17.2 remains sase-z4.6.5.4.6.3.

## Dependencies

- **Blocks:** [sase-z4.6.5.4.6.3](sase-z4.6.5.4.6.3.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.6.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.4.6.2.md) | [sase-z4.6.5.4.6.2](sase-z4.6.5.4.6.2.md) | 0 |
