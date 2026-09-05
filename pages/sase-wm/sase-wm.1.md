# Bead: sase-wm.1 — Project selector and structured check output for \`sase init\`

[Bead Pages](../README.md) / [sase-wm](README.md) / sase-wm.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.e.md) · **Assignee:** `sase-wm.1` · **Size:** medium
**Created:** 2026-09-04 11:58:56 EDT · **Closed:** 2026-09-04 15:35:34 EDT
**Plan:** [202609/projects\_tab\_init.md](https://github.com/sase-org/sase--plans/blob/main/202609/projects_tab_init.md)

## Description

cli: add the repeatable `-p/--project` selector beside `--all`, a `-j/--json` mode on `--check` with a schema version, per-planner `requires_tty` markers, and a status that distinguishes drift from blockers, lift the doctor plan serializer into `init_plan.py` without silent truncation, mirror the `--all`-with-subcommand dispatch guard for `-p`, and document both options.

## Notes

[2026-09-04T19:35:34Z · sase-wm.1] Verified: sase init -p NAME is repeatable and exclusive with --all/-M/subcommands; --check --json emits one schema_version=1 document whose top-level status distinguishes current/drift/blocked (same exit 1 for drift and blocked); requires_tty is set on owner-identity and sidecar-creation plans; doctor uses serialize_init_plan with an explicit actions_truncated marker; docs/init.md and docs/cli.md cover both options; just check passed.

## Dependencies

- **Blocks:** [sase-wm.2](sase-wm.2.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wm.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.1/README.md) | [sase-wm.1](sase-wm.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`07aa560`](https://github.com/sase-org/sase/commit/07aa560950bea6dfc99155071503bd0e18d093b5) | feat(init): add project selector and JSON check output | [sase-wm.1](sase-wm.1.md) | 2026-09-04 15:39:03 EDT |
