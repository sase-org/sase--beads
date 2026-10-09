# Bead: sase-1if.6 — Pre-install command preview

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.6` · **Size:** small
**Created:** 2026-10-08 15:26:25 EDT · **Closed:** 2026-10-09 05:25:09 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

command-preview: read an uninstalled plugin's declared sase_commands from its upstream pyproject.toml with a cache, expose it in plugin JSON and the install dry run, and flag collisions before install.

## Notes

[2026-10-09T09:24:44Z · sase-1if.6] PROPOSED FOLLOW-UP: just check lint (test waits) is red on tests/ace/tui/test_plan_decision_ace_stale.py:183,310 (inline-pause-wait); reproduces on trees without this phase work and is already tracked in sase-1hi.10.7.6 notes — detail

[2026-10-09T09:25:09Z · sase-1if.6] Implemented pre-install command preview: new declared_commands module (gh raw pyproject fetch, tomllib parse, declared_commands_cache.json keyed by full_name with updated_at+7d invalidation, mount-rule collision flags), declared_commands in plugin JSON for show/list -j, Adds-command chip + warnings in install -n panel and JSON, preview attached to TUI InstallPreview. Verified: 32 new + 191 neighboring tests green; gate fmt/ruff/mypy/flags/pyscripts/changelog/terminology green, symvision clean for touched files; test-waits red is pre-existing on untouched test_plan_decision_ace_stale.py (recorded as follow-up, tracked in sase-1hi.10.7.6); no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1if.5](sase-1if.5.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1if.7](sase-1if.7.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.6/README.md) | [sase-1if.6](sase-1if.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bd68ee4`](https://github.com/sase-org/sase/commit/bd68ee494200e697f60ed5abd009981726055941) | feat(plugins): pre-install plugin command preview (sase-1if.6) | [sase-1if.6](sase-1if.6.md) | 2026-10-09 05:27:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.1][1] | Check phase is open before keying epic-symbol rows to it | 1 |
| read-by | [agent:sase-1if.6][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.6/README.md

<!-- sase:referenced-by:end -->
