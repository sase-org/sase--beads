# Bead: sase-169.2 — Per-node salvage, recovery retries, and partial apply

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.2` · **Size:** medium
**Created:** 2026-09-22 10:18:00 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

salvage: in update mode, trust captures per test node instead of per run. Rerun failed or lost nodes a bounded number of times, apply every trusted change, and skip the rest with warnings under a new `partial` status. Downgrade whole-run evidence problems to "stale removal skipped" and exit 0.

## Dependencies

- **Blocks:** [sase-169.3](sase-169.3.md) ◐ · ⧖ 2026-09-22
- **Blocks:** [sase-169.4](sase-169.4.md) ◐ · ⧖ 2026-09-22
- **Blocks:** [sase-169.5](sase-169.5.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-169.2/README.md) | [sase-169.2](sase-169.2.md) | 0 |
