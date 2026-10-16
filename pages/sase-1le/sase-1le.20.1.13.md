# Bead: sase-1le.20.1.13 — Move agent, workspace, init, and VCS pages into reference/agents/ and reference/vcs/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.13

**Status:** ◐ in_progress · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.13` · **Size:** medium
**Created:** 2026-10-16 08:04:38 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Previously Closed

> ↺ Closed 2026-10-16T14:56:30Z · done
>
> (none)
>
> Reopened 2026-10-16T15:01:53Z by a status update

## Description

agents-vcs-move: split or move agent_sessions, workspace, agents_sidecar, init, vcs, and commit_workflows into reference/agents/ and reference/vcs/, with provider APIs, orchestrator, and sync internals going to contribute/.

## Notes

[2026-10-16T14:53:03Z · sase-1le.20.1.13] PROPOSED FOLLOW-UP: Repair the nine clean-base extensionless-tool mypy errors in unchanged tools/docs_split and tools/render_keymap_macro_reference — this run matches the failures recorded in sase-1le.20.1.3 note #1 and sase-1le.20.1.7 note #1; no matching task bead exists.

[2026-10-16T14:56:30Z · sase-1le.20.1.13] Completed the six documentation splits, generated pages, navigation and hygiene updates. Verified with just docs-check (pass), 42 focused tests (pass), git diff --check (pass), and epic-symbols (no leftovers). sase tool run check still fails on the nine unchanged clean-base mypy errors; recorded as PROPOSED FOLLOW-UP.

[2026-10-16T15:01:54Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not but the agent that was attempting to work on it failed.

[2026-10-16T15:16:07Z · sase-1le.20.1.13] PROPOSED FOLLOW-UP: Make docs_split anchor and nested-pointer generation match MkDocs — this recovery reproduced nine strict-build warnings from duplicate-heading suffixes (-1 versus _1), underscore stripping in VCS headings, and root-relative /reference/...md pointers. Added five explicit destination aliases, preserved three real underscore-bearing legacy anchor routes, and fixed two relative pointers in this phase; the splitter itself still needs regression coverage and repair.

## Dependencies

- **Depends on:** [sase-1le.20.1.12](sase-1le.20.1.12.md) ✓ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.14](sase-1le.20.1.14.md) ◐ · ⧖ 2026-10-16
- **Blocks:** [sase-1le.20.1.20](sase-1le.20.1.20.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.13/README.md) | [sase-1le.20.1.13](sase-1le.20.1.13.md) | 0 |
