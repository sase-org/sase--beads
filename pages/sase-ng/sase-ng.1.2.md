# Bead: sase-ng.1.2 — Restore MRU and unresolved-reference feedback on the durable launch path

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.2` · **Size:** small
**Created:** 2026-08-17 15:16:50 EDT · **Closed:** 2026-08-17 15:39:30 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

feedback: move VCS-xprompt MRU recording and the unresolved-xprompt-reference warning toast onto the durable path, so `<ctrl+p>` cycling keeps being fed and ACE keeps warning about unknown `#refs` once the orphaned body is deleted.

## Notes

[2026-08-17T19:39:01Z · sase-ng.1.2] PROPOSED FOLLOW-UP: force_reuse unauthorized-path tests over-specify segment_extra_env=None — tests/test_force_reuse_launch_seam.py::test_plain_sase_run_without_request_sidecar_still_rejects_forced_reuse and test_sidecar_without_authorization_still_rejects_forced_reuse assert launch_agents_from_cwd(prompt, segment_extra_env=None), but launch_query() only passes that kwarg when a force-reuse plan produced envs; unauthorized calls are launch_agents_from_cwd(query). Reproduced on the tree with this phase stashed. sase-ng.1.1 likely owns the assertion.

[2026-08-17T19:39:30Z · sase-ng.1.2] Moved VCS-xprompt MRU recording and the unresolved-#ref toast onto the durable sase run path. After a successful launch_query(), the leading get_ref_patterns() match is handed to record_vcs_xprompt_usage(); a plain prompt records nothing, #git:home is not persisted, an explicit #gh:sase is recorded once, and a failed spawn records nothing. scan_query_for_unresolved_references() results are also placed on emit_run_launch_result() as payload warning_messages via format_unresolved_references_toast(); _launch_outcome_from_completion() reads that key into LaunchProcOutcome and _on_launch_proc_complete() still toasts them. just check lint (fmt, ruff, mypy, symvision) passed; scoped tests 1663 passed. Two pre-existing force_reuse unauthorized-path assertions still fail without this phase's edits (PROPOSED FOLLOW-UP on this bead). No --epic-symbol leftovers.

[2026-08-17T19:40:37Z · sase-ng.1.2] Moved VCS-xprompt MRU recording and the unresolved-#ref toast onto the durable sase run path. After a successful launch_query(), the leading get_ref_patterns() match is handed to record_vcs_xprompt_usage(); a plain prompt records nothing, #git:home is not persisted, an explicit #gh:sase is recorded once, and a failed spawn records nothing. scan_query_for_unresolved_references() results are also placed on emit_run_launch_result() as payload warning_messages via format_unresolved_references_toast(); _launch_outcome_from_completion() reads that key into LaunchProcOutcome and _on_launch_proc_complete() still toasts them. just check lint (fmt, ruff, mypy, symvision) passed; scoped tests 1663 passed. Two pre-existing force_reuse unauthorized-path assertions still fail without this phase's edits (PROPOSED FOLLOW-UP on this bead). No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-ng.1.4](sase-ng.1.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.2/README.md) | [sase-ng.1.2](sase-ng.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`97f5b6f`](https://github.com/sase-org/sase/commit/97f5b6f03c277c165cb1d4c631a25006202e5574) | feat(launch): record VCS xprompt MRU and unresolved-ref toasts on durable sase run | [sase-ng.1.2](sase-ng.1.2.md) | 2026-08-17 15:41:29 EDT |
