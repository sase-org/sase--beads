# Bead: sase-ky.4 — Rewrite prose and remaining stored references

[Bead Pages](../README.md) / [sase-ky](README.md) / sase-ky.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zl.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zl.f1.md) · **Assignee:** `sase-ky.4` · **Size:** medium
**Created:** 2026-08-13 12:22:32 EDT · **Closed:** 2026-08-13 15:06:31 EDT
**Plan:** [plans:202608/plan\_ref\_kind\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_ref_kind_rename.md)

## Description

prose: update the documentation that describes the grammar, then sweep prose `plans:<path>` citations to `@plan:<path>` across docs, the plans sidecar, ~/.sase/plans, and the two small stored-data sites, without touching immutable history.

## Notes

[2026-08-13T19:05:52Z · sase-ky.4] PROPOSED FOLLOW-UP: `sase monitor start` fails with sase.agent._family_attach_types.FamilyAttachError: Cannot create agent family 'sase-ky': resolved parent is named 'sase-ky.5'. when invoked from a phase-bead agent whose lane sits under an epic whose currently-assigned child is a different phase bead (sase-ky.5, the land phase). Raised from promote_agent_to_family in src/sase/agent/_family_promotion.py:131, called from sase/monitor/start.py:147. Reproduced while working sase-ky.4 (phase prose) with: sase monitor start --command "just check" --reason "..." --timeout 45m --next "...". Worked around by running just check inline instead. Unrelated to the plans:->plan: rename content work; looks like a monitor/agent-family bug that could block other phase-bead agents from using sase monitor start.

[2026-08-13T19:06:31Z · sase-ky.4] Grammar docs updated: docs/artifact_references.md (compat paragraph now covers both @plans:/plans: aliases plus a new Provider Specs paragraph on ref-kind vs role-name independence), docs/sdd.md, docs/cli.md (x3), docs/ace.md now describe the plan: form; docs/change_spec.md, docs/editor.md, docs/configuration.md were already accurate (grammar-1 aliases) and needed no change. This repo's prose citations swept to @plan: (artifact_ref_prompt_context.py, builtin_entries.py, validate_sase_core_rs_version docstrings/comments) and src/sase/xprompts/skills/sase_artifact_file.md (generated skill source; redeploy via sase skill init --force is deferred until this change is committed+landed per sase/memory/generated_skills.md -- sase skill init --diff confirmed it only diffs against committed source). Swept the plans sidecar (sase repo open plans, separate git repo, 76 files changed) and ~/.sase/plans (plain machine-local dir, not git, 81 files changed) for prose plans:<path> -> @plan:<path>, using bare plan: (no @) for literal CLI-argument examples, machine-field UI-mockup rows (Path:/Epic Plan:), and parent: frontmatter keys. Left 3 files per tree completely untouched as immutable historical narrative where blind substitution would corrupt exact quoted data: this epic's own plan_ref_kind_rename.md, plan_artifact_file_reference_resolution.md (exact bug-repro strings), clan_summary_hint_targets.md (parser I/O demo with kind='plans' output tied to the old input). Caught and reverted two scripted-substitution false positives in both trees (auto_commit_qa_prompt_snapshot.md: sase-org/sase--plans:<path> is a repo-qualified path, not a ref; artifact_refs_and_prompt_bar.md: a Kind/Payload/Example grammar table row needed the bare form to match its unprefixed sibling rows). Fixed the two small stored-data sites: ~/.sase/file_reference_history.json (one @plans: entry -> @plan:), and verified ~/.sase/projects/gh_sase-org__sase/gh_sase-org__sase-archive.sase needed NO change -- its 4 raw plans: hits are all '*.plans:* changelog-scope entries (a documented non-goal, same pattern as CHANGELOG.md), and the narrow path-form grep finds zero real references there, so the epic plan's stated count for this site was inaccurate. Verified: grep -rn 'plans:[path-chars]' docs/ src/ tools/ returns nothing; grep -rn 'plans:' docs/ returns only the deliberate compat sentences plus the two YAML-role-key/non-goal hits (init.md, configuration.md, agents_sidecar.md); both sidecar trees clean under the same grep except the 3 deliberately-preserved files. just install + just check: fmt/lint/mypy/symvision all green, full non-visual scoped suite 29632 passed/10 skipped/2 failed (test_monitor_supervise.py::test_run_supervisor_completes_when_grandchild_holds_stdout, test_cli_work_cleanup.py::test_rollback_work_launch_uses_identity_aware_result_cleanup) -- both pass individually on a git-stash-clean tree, confirming pre-existing flakiness under the parallel scoped run's host contention (unrelated in subject matter to this doc/prose-only diff, no code files touched). Also hit and worked around an unrelated sase monitor start bug, recorded as a PROPOSED FOLLOW-UP note on this bead.

[2026-08-13T19:07:29Z · sase-ky.4] Docs (artifact_references.md, sdd.md, cli.md, ace.md) updated to describe plan: grammar; migrated plans:<path> citations to @plan:<path> across this repo, the plans sidecar (76 files), and ~/.sase/plans (81 files), leaving 3 files per tree with intentional immutable-history exceptions; fixed one ~/.sase/file_reference_history.json entry; verified archived Patch record file needed no changes. just check passed (lint/mypy/symvision clean); 2 pre-existing/flaky test failures confirmed unrelated via git-stash isolation.

## Dependencies

- **Depends on:** [sase-ky.2](sase-ky.2.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-ky.5](sase-ky.5.md) ◐ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ky.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ky.4/README.md) | [sase-ky.4](sase-ky.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b5e1ac8`](https://github.com/sase-org/sase/commit/b5e1ac88cbb7304f9457abf8d9aed0c353535e44) | docs: describe plan: grammar and migrate remaining plans: prose citations | [sase-ky.4](sase-ky.4.md) | 2026-08-13 15:08:25 EDT |
