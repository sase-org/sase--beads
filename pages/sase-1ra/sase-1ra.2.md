# Bead: sase-1ra.2 — A failed $EDITOR never deletes the typed draft (sase-1ce)

[Bead Pages](../README.md) / [sase-1ra](README.md) / sase-1ra.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18d.md) · **Assignee:** `sase-1ra.2` · **Size:** small
**Created:** 2026-11-04 17:59:13 EST · **Closed:** 2026-11-04 18:50:56 EST
**Plan:** [202611/next\_ten\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_ten_task_beads.md)

## Description

editor_drafts: on a non-zero editor exit or read failure, keep and recover changed prompt and workflow-YAML drafts instead of unlinking them (sase-1ce).

## Notes

[2026-11-04T23:48:06Z · sase-1ra.2] TASK RESOLVED: sase-1ce — _editor.py now preserves changed prompt drafts in Prompt Stash with source=editor_recovered and retains the scratch file; changed workflow drafts keep their file path. Focused regression tests pass (9/9), targeted mypy passes, and just check is still running.

[2026-11-04T23:50:48Z · sase-1ra.2] PROPOSED FOLLOW-UP: Re-triage the two pre-existing scoped-check failures reported by run 5998f201c03605d17b8e5ba5b2482a8f: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms (KNOWN; existing tracking bead sase-1hr, closed after a prior fixed-on-master verification) and tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed (FLAKY in this run; related historical tracking beads sase-1by and sase-tc, both closed). The editor changes do not touch these tests or their scanned call sites.

[2026-11-04T23:50:56Z · sase-1ra.2] Implemented editor draft recovery: changed prompts on editor failure/read failure are stashed with source=editor_recovered when readable and always retain the scratch file; failed workflow edits retain changed YAML and toast the path. Focused editor tests passed (9/9); targeted mypy and all lint stages passed. sase tool run check 5998f201c03605d17b8e5ba5b2482a8f had no new failures; its scoped test lane reported one historical KNOWN and one FLAKY failure, recorded as proposed follow-ups with existing tracking bead IDs. epic-symbol check is clear.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ra.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ra.2/README.md) | [sase-1ra.2](sase-1ra.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`522b07a`](https://github.com/sase-org/sase/commit/522b07a009895c6f20b4a9db16b9f8103e3c2dfe) | fix(ace): preserve failed editor drafts | [sase-1ra.2](sase-1ra.2.md) | 2026-11-04 18:52:47 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ra.2][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ra.2/README.md

<!-- sase:referenced-by:end -->
