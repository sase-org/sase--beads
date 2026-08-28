# Bead: sase-ud.13.1 — Collapse the gate-shell status machinery and remove the beta flag

[Bead Pages](../README.md) / [sase-ud.13](sase-ud.13.md) / sase-ud.13.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.md) · **Assignee:** `sase-ud.13.1.land`
**Created:** 2026-08-27 08:49:03 EDT
**Plan:** [202608/gate\_shell\_status\_collapse.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/gate_shell_status_collapse.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/gate_shell_status_collapse.md

<!-- sase:links:end -->

## Description

The gate shell is the only thing that publishes a plan or question status: the `gate_shell_handoff` beta flag and its blocking Off branch are gone, the notification and family-policy status overrides that existed only to give a blocked plan chain a visible row are gone, the agent-list colour ladder is one shared pair-accent path over declared gate accents, and the flat `monitor_*` / `gate_*` wire blocks are one nested `family_shell` record at wire schema v7.

## Notes

[2026-08-27T15:59:39Z · 0ew] DISCOVERED ISSUE: While verifying unrelated plan:202608/pager_screen.md on 2026-08-27, `just check` failed in `_setup` before lint/tests after rebuilding linked sase-core 0.32.9 from the linked checkout: `[validate_sase_core_rs] scan_agent_artifacts probe returned stale schema: got 7, expected 6`; exit 1. The pager diff only touches pager/ACE view-file modules and tests and passes focused pytest, ruff, mypy, and visual lanes, so this is not caused by the pager-screen change. It is causally linked here because child phase `sase-ud.13.1.5` intentionally bumped the agent-scan wire schema to 7 in sase-core; this checkout Python-side validator still expects 6 until the phase Python/schema update is integrated here or the linked-core checkout is brought back into the compatible window.

[2026-08-28T11:12:13Z · 0fd--code] DISCOVERED ISSUE: While verifying unrelated plan:202608/pager_hint_highlight_boundary.md on 2026-08-28, required `just check` passed Python formatting, Markdown formatting, keep-sorted, Ruff, and mypy, then failed only the feature-flag lint: `rule 8: live flag bead 'sase-uo' has no definition (key 'gate_shell_handoff'); created 2026-08-27T03:11:59Z by bbugyi200.athena.sase-ud.10 — add the registry definition or close the bead`. This is not caused by the pager diff, which only touches `src/sase/pager/_labels.py`, pager label tests, and pager PNG snapshots. It is causally linked to this epic because closed child phase `sase-ud.13.1.2` explicitly removed the `gate_shell_handoff` flag and its description includes closing flag bead `sase-uo`; the current tree has removed the definition while the flag bead still appears live, so `tools/check_feature_flags` fails before the scoped test lane can run.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.13.1.land/README.md) | [sase-ud.13.1](sase-ud.13.1.md) | 0 |
