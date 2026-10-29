# Bead: sase-1pi.2 — Only merge-capable release-plz runs count as core cuts for the steward

[Bead Pages](../README.md) / [sase-1pi](README.md) / sase-1pi.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15m.md) · **Assignee:** `sase-1pi.2` · **Size:** medium
**Created:** 2026-10-28 20:07:12 EDT · **Closed:** 2026-10-28 21:28:47 EDT
**Plan:** [202610/unblock\_e2\_core\_release\_flow.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_e2_core_release_flow.md)

## Description

real-cuts: the steward's cut facts drop push and six-hourly heal runs, which never merge the release PR. CORE_LAG then proposes a real cut, and a non-merging success no longer supersedes a failed cut. The cut_budget decision bounds how often the steward dispatches. Prove it with a live read-only --once.

## Notes

[2026-10-29T01:28:47Z · sase-1pi.2] real-cuts done. Reader keeps only schedule/dispatch runs whose Merge release PR job ran (push/heal/dry-run excluded; in-flight schedule/dispatch kept), each cut tagged event+started_at. Rust policy cut_budget=daily: dispatch proposed only with merge authority on and no workflow_dispatch cut started earlier the same UTC day, else suppressed naming the rule. Verified: 7 new Rust tests + full sase-core check pass; 5 new + 4 fixed Python reader tests, decide/cli/sinks, and sase check pass; live read-only --once exits 0 (core_ci_red, macos-core owns it) and live cuts show 267 push runs in 30d with zero in cuts. Notes left on sase-1n6 and sase-1oe.4. Core-side edits unlanded in linked checkout; land core first, then move sase-core-revision.txt past the core commit in the same sase land.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pi.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pi.2/README.md) | [sase-1pi.2](sase-1pi.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@95dc0c1`](https://github.com/sase-org/sase-core/commit/95dc0c10db564ad31bc7e63761dd4a6fab4f40e3) | feat(release-steward): bound core-cut dispatches to one per UTC day with merge authority | [sase-1pi.2](sase-1pi.2.md) | 2026-10-28 21:30:14 EDT |
