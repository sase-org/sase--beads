# Bead: sase-j8.1 — Rename the sase vcs CLI command to sase stitch

[Bead Pages](../README.md) / [sase-j8](README.md) / sase-j8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xn/README.md) · **Assignee:** `sase-j8.1` · **Size:** medium
**Created:** 2026-08-10 16:18:31 EDT · **Closed:** 2026-08-10 17:03:39 EDT
**Plan:** [202608/stitch\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_rename.md)

## Description

cli: rename the `sase vcs` command tree to `sase stitch`, keep `vcs` as a registered legacy alias with facade modules, and update the compact root help, parser/handler modules, tests, and CLI/VCS/configuration docs.

## Notes

[2026-08-10T21:01:59Z · sase-j8.1] PROPOSED FOLLOW-UP: sase stitch list renders the repository constellation, not stitches, and overlaps sase repo list. Consider moving repo-constellation listing under sase repo so bare sase stitch can default to the commit/stitch timeline.

[2026-08-10T21:03:07Z · sase-j8.1] PROPOSED FOLLOW-UP: check-full flake baseline gate reports tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree as a new reproducible flake; triage or file the required flake bead before landing.

[2026-08-10T21:03:39Z · sase-j8.1] Implemented the CLI rename to sase stitch with legacy vcs aliases; verified focused parser/root-help tests, CLI help for stitch and vcs, just check passed, and just check-full passed test-cost but failed only the existing flake-baseline gate for tests/test_bead/test_plus_one_presentation.py::test_post_close_plus_one_badge_marker_search_and_json_agree; follow-up noted.

[2026-08-10T21:05:12Z · sase-j8.1] Verified focused parser/default/root-help tests, CLI help for stitch and legacy vcs, just check; just check-full reached only the flake-baseline gate noted on the bead.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j8.1/README.md) | [sase-j8.1](sase-j8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`83e3d3c`](https://github.com/sase-org/sase/commit/83e3d3c274be7baf5f59d3d28040e1e1bcf0d383) | feat(cli): rename vcs command to stitch | [sase-j8.1](sase-j8.1.md) | 2026-08-10 17:07:34 EDT |
