# Bead: sase-i8.2 — Python wire mirror and skew probes

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.2` · **Size:** small
**Created:** 2026-08-09 09:43:21 EDT · **Closed:** 2026-08-09 10:48:42 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

wire: mirror the Rust contract on the Python side — parent ids and schema 3 in the wire module, %P in the pinned git-log format, the tolerant golden parser, a merge-summary facade — and add the validator probes that make wheel/host skew fail loudly instead of silently returning zero commits.

## Notes

[2026-08-09T14:48:09Z · sase-i8.2] PROPOSED FOLLOW-UP: tools/validate_sase_core_rs has 3 pre-existing mypy errors (union-attr on _validate_project_lifecycle_contract dict|None access, lines ~561/564/567) that just check never catches because pyproject.toml [tool.mypy].files is scoped to "src" only, excluding tools/. Widen the mypy file scope (or add a dedicated tools/ mypy stage) so this class of bug is caught.

[2026-08-09T14:48:42Z · sase-i8.2] Mirrored the sase-core schema-3 VCS-log wire contract in Python: VCS_LOG_WIRE_SCHEMA_VERSION=3, VcsCommitWire gained a kw_only parent_ids tuple (defensively rehydrated from missing/absent dict keys) and an is_merge property; VCS_LOG_GIT_FORMAT now emits %P before %s, and _parse_git_log_python tolerantly accepts both the legacy 7-field and current 8-field record layouts, matching the Rust parser's rules exactly (root-commit empty parents, octopus multi-parent). Added a merge_summary(subject, body) facade over the new parse_merge_summary binding, returning a frozen MergeSummary or None. tools/validate_sase_core_rs now requires vcs_log_wire_schema_version and parse_merge_summary in REQUIRED_BINDINGS and asserts vcs_log_wire_schema_version()==3 via a new _validate_vcs_log_wire_schema probe, so wheel/host skew on this contract fails loudly instead of silently dropping every commit. Whitelisted MergeSummary/merge_summary in Justfile's symvision invocation as sase-i8 epic symbols (consumed by later render/tui phases). Verified: rebuilt sase_core_rs from the sase-core checkout at commit 459bbc6 (parent ids, tolerant parser, merge summary, schema 3) via just install; ran the new/updated tests in tests/test_core_vcs_log.py and tests/test_validate_sase_core_rs_tool.py (all passing); ran tools/validate_sase_core_rs --sase-core-dir directly against the installed wheel (exit 0); ran just check (passed, full-suite escalation triggered by the Justfile/core-checkout change) and then just check-full (passed: every lint gate including symvision, full test suite, flake baseline).

[2026-08-09T14:50:42Z · sase-i8.2] Added parent_ids/is_merge to VcsCommitWire (schema v3), merge_summary() facade over parse_merge_summary binding, validator tool schema-3 probe, and Justfile epic-symbol whitelist entries. Verified: just check and just check-full both pass; validator tool passes directly against installed sase_core_rs wheel; 37 tests pass in test_core_vcs_log.py.

## Dependencies

- **Depends on:** [sase-i8.1](sase-i8.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.3](sase-i8.3.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.2/README.md) | [sase-i8.2](sase-i8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f5fb724`](https://github.com/sase-org/sase/commit/f5fb72438ce5aa4dc18a00a5b003791699bc180a) | feat(vcs): mirror merge-commit parent ids in Python wire layer | [sase-i8.2](sase-i8.2.md) | 2026-08-09 10:53:22 EDT |
