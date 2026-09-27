# Bead: sase-1bd.4 — Update panel failure row and docs polish

[Bead Pages](../README.md) / [sase-1bd](README.md) / sase-1bd.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2d.md) · **Assignee:** `sase-1bd.4` · **Size:** small
**Created:** 2026-09-27 13:23:05 EDT · **Closed:** 2026-09-27 16:35:31 EDT
**Plan:** [202609/update\_gear\_states.md](https://github.com/sase-org/sase--plans/blob/main/202609/update_gear_states.md)

## Description

panel-failure-row: surface the recorded failure as the first Update panel (,U) row. f opens the failure report, and d dismisses in place through a panel message. The open panel refreshes when the journal view changes, and the Update-panel docs describe the row.

## Notes

[2026-09-27T20:35:11Z · sase-1bd.4] PROPOSED FOLLOW-UP: symvision whole-repo gate fails identically on clean base (dozens of unused-symbol flags in unrelated files, e.g. finalizer_run_view, agent tabs); none in update-panel files — triage as tech debt

[2026-09-27T20:35:31Z · sase-1bd.4] Panel failure row landed: build_update_panel_state(last_failure=) projects a first 'failure' row (key f, failed/interrupted title, ✗ failed chip, UPDATE_FAILED_ACCENT, detail truncated to row width); UpdatePanel binds f/F to open the report and d to post DismissFailureRequested in place with hint toggle; shortcut/refresh pass last_failure, failure result opens the report, dismiss handler + _apply_update_attempts_view refresh the open panel; docs/ace.md documents row and keys. Verified: 112 focused tests pass (panel state/modal/shortcut/attempt-state/indicator), ruff+format+mypy clean, symvision identical to clean base (pre-existing failures noted as follow-up), default_config.yml needs no keymap entries, no epic-symbols remain. Full sase tool run check could not finish inline (rust-install compile exceeds turn limit).

## Dependencies

- **Depends on:** [sase-1bd.3](sase-1bd.3.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bd.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bd.4/README.md) | [sase-1bd.4](sase-1bd.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`21d4e12`](https://github.com/sase-org/sase/commit/21d4e12c8c43c56ebeaa24ff245e7eafbd13c9b5) | feat(update-panel): surface recorded failure as first Update panel row (sase-1bd.4) | [sase-1bd.4](sase-1bd.4.md) | 2026-09-27 16:37:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bd.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bd.4/README.md

<!-- sase:referenced-by:end -->
