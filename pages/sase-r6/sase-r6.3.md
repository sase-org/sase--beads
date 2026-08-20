# Bead: sase-r6.3 — Host-owned limit token on every Artifacts pane

[Bead Pages](../README.md) / [sase-r6](README.md) / sase-r6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.086](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.086.md) · **Assignee:** `sase-r6.3` · **Size:** medium
**Created:** 2026-08-19 17:09:40 EDT · **Closed:** 2026-08-19 20:00:07 EDT
**Plan:** [202608/load\_more\_ctrl\_j.md](https://github.com/sase-org/sase--plans/blob/main/202608/load_more_ctrl_j.md)

## Description

query-limit: accept limit:N on every Artifacts dialect, inject it into each pane's default query, and apply it as a post-match cap.

## Notes

[2026-08-19T23:59:09Z · sase-r6.3] PROPOSED FOLLOW-UP: PNG goldens for default Artifacts queries — Stitches/Beads/Files/Plans/Patches persistent filter rows now include limit:<page_size>; artifacts-keys should inspect .pytest_cache/sase-visual and update goldens with --sase-update-visual-snapshots if pixels change.

[2026-08-19T23:59:32Z · sase-r6.3] PROPOSED FOLLOW-UP: flake test_ace_page_fast_startup_is_structurally_quiet — once failed under full-suite just check with a cancelled sase-artifacts-project-choices pump-free task still in _pump_free_async_tasks; isolated rerun passed.

[2026-08-20T00:00:07Z · sase-r6.3] limit:N is a host-owned cap on every Artifacts dialect: extracted before parse/Rust eval, sliced after match, injected into each pane default via ensure_limit(page_size). Completions, highlighting, help, and docs updated. just check passed (escalated full suite). epic-symbols for sase-r6.3 cleared.

[2026-08-20T00:01:08Z · sase-r6.3] limit:N is a host-owned cap on every Artifacts dialect: extracted before parse/Rust eval, sliced after match, injected into each pane default via ensure_limit(page_size). Completions, highlighting, help, and docs updated. just check passed (escalated full suite). epic-symbols for sase-r6.3 cleared.

## Dependencies

- **Depends on:** [sase-r6.1](sase-r6.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r6.4](sase-r6.4.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r6.3/README.md) | [sase-r6.3](sase-r6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6b0b1e3`](https://github.com/sase-org/sase/commit/6b0b1e3f9ac223586a36825dc3dd5b48516f02a1) | feat(ace): apply host-owned limit:N cap on every Artifacts pane | [sase-r6.3](sase-r6.3.md) | 2026-08-19 20:03:05 EDT |
