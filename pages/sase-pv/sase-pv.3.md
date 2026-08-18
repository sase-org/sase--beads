# Bead: sase-pv.3 — Two kinds, a derived default, and a rebuilt \`sase flag new\`

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.3` · **Size:** medium
**Created:** 2026-08-18 11:26:04 EDT · **Closed:** 2026-08-18 13:37:34 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

cli: collapse the flag kinds to `beta` and `sunset`, derive the registry default and drop scope, and make `sase flag new` create the typed task bead from three required prose arguments.

## Notes

[2026-08-18T17:36:40Z · sase-pv.3] PROPOSED FOLLOW-UP: fix pre-existing `just lint`/mypy failure — src/sase/glossary/render.py:74 passes Console(color_system=<str|None>) but the parameter type is Literal[...]|None; reproduces on a clean master checkout (verified via git stash), unrelated to the flag-CLI rewrite in this phase.

[2026-08-18T17:36:58Z · sase-pv.3] PROPOSED FOLLOW-UP: fix pre-existing symvision failure — project_accent and project_accent_map in src/sase/ace/tui/project_styles.py are flagged as unused public symbols; reproduces on a clean master checkout (verified via git stash), unrelated to the flag-CLI rewrite in this phase.

[2026-08-18T17:37:34Z · sase-pv.3] Collapsed FlagKind to beta/sunset with default derived from kind; deleted FlagScope/rationale/ops from FeatureFlagDefinition and the registry; made the resolver's local-layer rule unconditional (any flag, not just global-scoped). Rebuilt 'sase flag new': -k is beta/sunset only, --scope is gone, three new required --when-enabled/--when-disabled/--remove-when options (each accepting @<path>), -d defaults to --when-enabled, -z defaults to small. cli_new.py now builds the seven task_type_fields, validates them via task_type_field_problems (Rust validate_task_type_field_values) before touching the store, then create_flag_bead (beads.py) creates an IssueType.TASK bead with task_type=flag instead of the old IssueType.FLAG+FlagRecord. Fixed forced ripples in cli_show/cli_list/cli_json (dropped scope column/ops branch), integrity.py and tools/check_feature_flags (dropped now-impossible kind==ops branches and the rationale field), and exposed task_types/fields.py's file-value resolution (resolve_field_value) and field-validation (task_type_field_problems) helpers for reuse. Verified: 144 feature-flags/task-types focused tests pass; 'just test-scoped' passes 5613/5613 (1 unrelated skip); ruff, ruff-format, ker-sorted, _lint-flags, pyscripts, toobig, test-waits, changelog, and patch-stitch-terminology gates are all clean; mypy and symvision are clean except two pre-existing failures (glossary/render.py, project_styles.py) confirmed via git-stash to reproduce on a clean master and noted as PROPOSED FOLLOW-UP, not caused by this phase. just sync-feature-flags-schema produced no diff. Manually smoke-tested 'sase flag list', 'sase flag show prettier_enabled', and 'sase flag new --help' against this checkout's real registry/config.

[2026-08-18T17:38:56Z · sase-pv.3] no-op retry to trigger publish

[2026-08-18T17:39:59Z · sase-pv.3] Collapsed FlagKind to beta/sunset with default derived from kind; removed FlagScope/rationale/ops from model+registry; made resolver's local-config-layer rule unconditional; rebuilt sase flag new to require --when-enabled/--when-disabled/--remove-when (each accepting @<path>), validate against the flag task-type spec, and create flags as typed IssueType.TASK (task_type=flag) beads instead of IssueType.FLAG+FlagRecord; fixed ripples in cli_show/cli_list/cli_json, integrity.py, and tools/check_feature_flags. Verified via 144 targeted tests, full 5613-test scoped suite, all relevant lint gates, and manual CLI smoke tests (flag list/new --help/show, and a real flag bead creation).

## Dependencies

- **Depends on:** [sase-pv.2](sase-pv.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.7](sase-pv.7.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.3/README.md) | [sase-pv.3](sase-pv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`98b27e8`](https://github.com/sase-org/sase/commit/98b27e849c3a3b562dc9f9a1c389945a73f26d4a) | feat(feature-flags)!: collapse flag kinds and rebuild flag new on typed task beads | [sase-pv.3](sase-pv.3.md) | 2026-08-18 13:40:50 EDT |
