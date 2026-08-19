# Bead: sase-qt.3 — ace.keymaps.memory binding scope

[Bead Pages](../README.md) / [sase-qt](README.md) / sase-qt.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md) · **Assignee:** `sase-qt.3` · **Size:** small
**Created:** 2026-08-19 08:16:37 EDT · **Closed:** 2026-08-19 08:47:40 EDT
**Plan:** [202608/ace\_memory\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)

## Description

panel-keymaps: register the panel-scoped keymap dataclass, defaults, config schema, binding builders, and app help sections.

## Notes

[2026-08-19T12:34:55Z · sase-qt.3] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-qu (key ref_sync_gesture) with no definition in this tree — unrelated to panel-keymaps; blocks just check for every agent until the flag is registered or the bead is closed.

[2026-08-19T12:46:46Z · sase-qt.3] PROPOSED FOLLOW-UP: flake tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet failed once in the escalated full suite with a leftover cancelled artifacts-project-choices task, then passed on the same tree — not caused by panel-keymaps.

[2026-08-19T12:47:02Z · sase-qt.3] PROPOSED FOLLOW-UP: ci tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection is stale — marker now includes tests/test_suite_gate_budget.py, test_suite_gate_lease.py, and test_suite_gate_reclaim.py; refresh with just refresh-contract-manifest. Unrelated to panel-keymaps.

[2026-08-19T12:47:40Z · sase-qt.3] Registered ace.keymaps.memory everywhere the glossary scope is wired (MemoryPanelKeymaps, default_config.yml, schema, loaders, binding builders, and app help sections). Verified defaults cover every dataclass field; unknown-action warning, invalid-key revert, duplicate-key revert, and scoped overlap with app keys all behave like glossary; help listings include Memory Panel on patches/agents/axe. Remaining lint/validate/symvision passed. just check flag lint failed on unrelated live flag bead sase-qu (ref_sync_gesture). Escalated full suite: 33901 passed; two unrelated failures recorded as PROPOSED FOLLOW-UP.

[2026-08-19T12:49:01Z · sase-qt.3] Registered ace.keymaps.memory everywhere the glossary scope is wired (MemoryPanelKeymaps, default_config.yml, schema, loaders, binding builders, and app help sections). Verified defaults cover every dataclass field; unknown-action warning, invalid-key revert, duplicate-key revert, and scoped overlap with app keys all behave like glossary; help listings include Memory Panel on patches/agents/axe. Remaining lint/validate/symvision passed. just check flag lint failed on unrelated live flag bead sase-qu (ref_sync_gesture). Escalated full suite: 33901 passed; two unrelated failures recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-qt.4](sase-qt.4.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.3/README.md) | [sase-qt.3](sase-qt.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f388474`](https://github.com/sase-org/sase/commit/f388474d67f78c9c0ff81e0f446fb2afc0729367) | feat(ace): register focused Memory panel keymap scope | [sase-qt.3](sase-qt.3.md) | 2026-08-19 08:49:44 EDT |
