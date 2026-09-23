# Bead: sase-169.2 — Per-node salvage, recovery retries, and partial apply

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.2` · **Size:** medium
**Created:** 2026-09-22 10:18:00 EDT · **Closed:** 2026-09-22 12:19:52 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

salvage: in update mode, trust captures per test node instead of per run. Rerun failed or lost nodes a bounded number of times, apply every trusted change, and skip the rest with warnings under a new `partial` status. Downgrade whole-run evidence problems to "stale removal skipped" and exit 0.

## Notes

[2026-09-22T15:01:03Z · sase-169.2] PROPOSED FOLLOW-UP: proof run 0cb33882 refreshed agents_family_panel_shells_gate_120x40.png (531 material pixels, twice-verified) and it was reverted; the docs phase full run should re-triage it as UNRELATED_SCREENSHOT_UPDATES or a genuine refresh

## Dependencies

- **Blocks:** [sase-169.3](sase-169.3.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-169.4](sase-169.4.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-169.5](sase-169.5.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-169.2/README.md) | [sase-169.2](sase-169.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7f01925`](https://github.com/sase-org/sase/commit/7f019258b1bfa1523786632d0f85d2b4bab12cf6) | feat(screenshots): salvage per-node captures with recovery retries and partial apply | [sase-169.2](sase-169.2.md) | 2026-09-22 11:32:01 EDT |
