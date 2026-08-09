# Bead: sase-i1.3 — Python CLI flag, rendering, tests, and docs

[Bead Pages](../README.md) / [sase-i1](README.md) / sase-i1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w8/README.md) · **Assignee:** `sase-i1.3` · **Size:** medium
**Created:** 2026-08-09 07:42:01 EDT · **Closed:** 2026-08-09 08:44:37 EDT
**Plan:** [202608/bead\_search\_regex.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex.md)

## Description

cli: add the `-e`/`--regex` option to the `sase bead search` argparse parser, plumb it through the bead read facade and BeadProject, handle invalid patterns and regex snippet selection in the Python renderer, and update the bead search tests and documentation.

## Notes

[2026-08-09T12:44:04Z · sase-i1.3] PROPOSED FOLLOW-UP: flake baseline gate has three new reproducible flake entries — tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_directory_key_spelling_also_resolves, tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_offers_project_local_xprompts_by_canonical_name, and tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor exceeded tests/reproducible_flake_baseline.txt during check-full after full pytest passed.

[2026-08-09T12:44:37Z · sase-i1.3] Verified just install, focused pytest for bead search/fast-path/project/facade coverage, and just check. just check-full passed the full pytest lane, then failed only the unrelated flake-baseline gate for three new reproducible flake entries; recorded that as a PROPOSED FOLLOW-UP on this phase bead.

[2026-08-09T12:45:56Z · sase-i1.3] Verified just install, focused search tests, just check; just check-full passed the full pytest lane and only failed the unrelated flake-baseline health gate, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-i1.2](sase-i1.2.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.3/README.md) | [sase-i1.3](sase-i1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a3a536a`](https://github.com/sase-org/sase/commit/a3a536a033daebf647439bde081d7e609a8dc99e) | feat(bead): add regex mode to bead search | [sase-i1.3](sase-i1.3.md) | 2026-08-09 08:46:44 EDT |
