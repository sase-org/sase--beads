# Bead: sase-1aa.2 — Move built-in provider model data and size aliases into one manifest

[Bead Pages](../README.md) / [sase-1aa](README.md) / sase-1aa.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1t](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1t.md) · **Assignee:** `sase-1aa.2` · **Size:** medium
**Created:** 2026-09-25 22:26:18 EDT · **Closed:** 2026-09-26 06:09:38 EDT
**Plan:** [202609/model\_catalog\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_catalog_maintenance.md)

## Description

unified_manifest: add a strictly validated, lazy models.yml loader and migrate seven provider hooks and tier invocation defaults while preserving current metadata and completion output.

## Notes

[2026-09-26T10:08:56Z · sase-1aa.2--2] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget flaked under full-suite parallel load (5.21s CPU vs 5.0s budget, loadavg ~3-4, 7 workers); passes solo on this tree (4.23s, 3365 modules < 3400 cap) and on clean base — timing-sensitive, unrelated to model-manifest change

[2026-09-26T10:09:14Z · sase-1aa.2--2] PROPOSED FOLLOW-UP: tests/test_models_panel_actions.py::test_alias_actions_on_bucket_are_guarded[o] flaked under full-suite load (OptionDoesNotExist bucket:research, 1 of 4 identical params); passes solo on this tree and clean base; views are fully mocked so manifest change cannot affect it

[2026-09-26T10:09:38Z · sase-1aa.2--2] Manifest work verified: 70 touched-area tests pass (model_manifest, alias defaults, advisories, render docs, models panel); lint gates incl. symvision green with no epic-symbol leftovers; full just check reached 47880 passed with only 2 load flakes that pass solo on this tree and clean base (recorded as PROPOSED FOLLOW-UPs)

## Dependencies

- **Depends on:** [sase-1aa.1](sase-1aa.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-1aa.3](sase-1aa.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aa.2.md) | [sase-1aa.2](sase-1aa.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1ef56bd`](https://github.com/sase-org/sase/commit/1ef56bd1b696af2de86705af38c1c7321686926f) | feat(llm-provider): move built-in model data and size aliases into one manifest | [sase-1aa.2](sase-1aa.2.md) | 2026-09-26 06:11:53 EDT |
