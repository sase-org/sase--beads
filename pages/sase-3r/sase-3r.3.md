# Bead: sase-3r.3 — Phase 3: Loader, Tree, and Root Status Behavior

[Bead Pages](../README.md) / [sase-3r](README.md) / sase-3r.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-3r.3`
**Created:** 2026-05-17 00:19:03 UTC · **Closed:** 2026-05-17 01:14:31 UTC
**Plan:** [202605/agent\_families\_2.md](https://github.com/sase-org/sase--plans/blob/main/202605/agent_families_2.md)

## Notes

COMMIT: f14071a65

[2026-07-27T18:58:30Z · sase-a1.6] [2026-05-17T01:13:26Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Completed loader/tree/root-status phase: TUI agent model now carries family metadata, family roots gain/logically use planner children, root status mirrors the newest family child, grouping avoids accidental bead-id family parsing, and copy/wait/resume prompts use the root family name for root rows. Verified with focused pytest suites and full just check.

## Dependencies

- **Depends on:** [sase-3r.2](sase-3r.2.md) ✓
- **Blocks:** [sase-3r.4](sase-3r.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`f7b157e`](https://github.com/sase-org/sase/commit/f7b157e79574a36c90b2d64af6c08d99b6f47909) | feat: wire visibility-aware inbox query into TUI loader (sase-3r.3) | [sase-3r.3](sase-3r.3.md) | 2026-05-16 14:55:33 |
| [`39fe1af`](https://github.com/sase-org/sase/commit/39fe1afe9724d1bc000e327346d2f08ded5f7b4d) | feat: mirror agent family root status in TUI (sase-3r.3) | [sase-3r.3](sase-3r.3.md) | 2026-05-17 01:14:57 |
