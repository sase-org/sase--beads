# Bead: sase-18j.8 — sase tool failures and triage in verify-monitor follow-ups

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.8` · **Size:** medium
**Created:** 2026-09-24 19:07:13 EDT · **Closed:** 2026-09-25 16:28:05 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

## Description

failures-and-followups: add the sase tool failures subcommand over the Rust aggregation, and a flag-gated Failure triage section in verify-monitor follow-up prompts, for both reserved runs and wrapped raw just check.

## Notes

[2026-09-25T20:27:26Z · sase-18j.8] PROPOSED FOLLOW-UP: validate_sase_core_rs scan_agent_artifacts expected schema 9, linked origin/master returns 10 — same pin-lag pattern as closed sase-oq; `_setup` / `just check` fail before lint. Reproduced after workspace setup fast-forwarded sase-core; not caused by this phase.

[2026-09-25T20:27:45Z · sase-18j.8] PROPOSED FOLLOW-UP: symvision reports private `_OwnerRecordLookup` imported from src/sase/bead/cli_work_cleanup_selection.py (TYPE_CHECKING). Unmodified on this tree; reproduces independently of sase-18j.8.

[2026-09-25T20:28:05Z · sase-18j.8] Shipped ungated `sase tool failures` over tool_run_failures (table + versioned -j, cwd catalog default, empty exits 0, linked-repo groups isolated) and a flag-gated ## Failure triage section in verify-monitor follow-ups for reserved runs and monitor-owned wrapped just check. Parser/completion spec updated; leftover epic-symbols re-keyed to sase-18j.7. Verified: parser tests, DoD-9 failures tests, DoD-10 follow-up tests both flag states, completion snapshot, ruff, mypy on touched files, symvision (only pre-existing _OwnerRecordLookup).

## Dependencies

- **Depends on:** [sase-18j.6](sase-18j.6.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18j.9](sase-18j.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18j.8/README.md) | [sase-18j.8](sase-18j.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`89868a9`](https://github.com/sase-org/sase/commit/89868a90b2e48eae1de60c8d24ce35682bbe46fc) | feat(tool): add sase tool failures and follow-up triage | [sase-18j.8](sase-18j.8.md) | 2026-09-25 17:35:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18j.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18j.8/README.md

<!-- sase:referenced-by:end -->
