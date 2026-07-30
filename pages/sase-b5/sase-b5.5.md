# Bead: sase-b5.5 — Regenerate degraded pages and verify the sase-b3 lineage end to end

[Bead Pages](../README.md) / [sase-b5](README.md) / sase-b5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b5.5` · **Size:** small
**Created:** 2026-07-30 11:20:34 UTC · **Closed:** 2026-07-30 13:30:32 UTC
**Plan:** [202607/bead\_page\_association\_anchors.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_page_association_anchors.md)

## Description

repair: republish every generated bead page from the corrected projection, confirm the sase-b3 lineage reports the associations its commits prove, and add a guard that fails when a published page links a commit to a sidecar remote.

## Notes

[2026-07-30T13:30:32Z · sase-b5.5] Republished all generated bead pages from the corrected projection (sase bead pages refresh --write, 497 pages changed of 2389 scanned, committed to the beads sidecar as 65d6af4); 1892 unaffected pages stayed byte-identical, confirming the label-churn constraint held. Verified pages/sase-b3/README.md against the plan's target state: sase-b3.1-b3.5 now report 1 commit each linked to sase-core, sase-b3.6-b3.8 1 each linked to the primary repo, sase-b3.9 3 (2 primary + 1 sase--plans), every non-primary commit qualified as <repo>@<sha> and linked to its own remote, and every agent row linked into the agents sidecar. Added a durable guard: src/sase/bead_pages/audit.py detects unqualified (primary-claiming) commit links that resolve against another repository's remote, a new project.bead_pages doctor check reports them as ERROR with a refresh next step, and a publication-level regression test asserts a sidecar-driven publication produces zero such links. The guard reproduced the defect before the repair (29 findings: 23 sase--plans, 6 sase-core - six more than the plan predicted) and reports OK after. just check passes except a pre-existing plan-link error for another agent's in-flight sase-b7 plan in the plans sidecar; full test suite green (24203 passed).

## Dependencies

- **Depends on:** [sase-b5.2](sase-b5.2.md) ✓
- **Depends on:** [sase-b5.3](sase-b5.3.md) ✓
- **Depends on:** [sase-b5.4](sase-b5.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b5.5/README.md) | [sase-b5.5](sase-b5.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f62e8cd`](https://github.com/sase-org/sase/commit/f62e8cd01713c934cb6e5fcf0374667805a78ceb) | feat(bead-pages): guard against misattributed commit links | [sase-b5.5](sase-b5.5.md) | 2026-07-30 13:31:35 |
