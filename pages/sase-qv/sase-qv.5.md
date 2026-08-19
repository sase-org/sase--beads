# Bead: sase-qv.5 — Agent family container status

[Bead Pages](../README.md) / [sase-qv](README.md) / sase-qv.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07k.md) · **Assignee:** `sase-qv.5` · **Size:** small
**Created:** 2026-08-19 09:14:33 EDT · **Closed:** 2026-08-19 12:26:56 EDT
**Plan:** [202608/monitor\_custom\_statuses.md](https://github.com/sase-org/sase--plans/blob/main/202608/monitor_custom_statuses.md)

## Description

family: mirror a monitor's custom status onto its agent family container row for plain families as well as plan roots, and copy the status pair so the mirrored row renders in the same accent as the monitor itself.

## Notes

[2026-08-19T16:26:28Z · sase-qv.5] PROPOSED FOLLOW-UP: just check fails at `init memory --check` — the `feature` task-type spec digest changed and generated memory/instruction shims need `sase memory init`; that requires explicit user permission, so this phase did not run it. Lint (fmt/ruff/mypy/symvision/toobig) passed after re-keying stale sase-qt.6/sase-qt.7 --epic-symbol entries to sase-qt and privatizing unused in-file classify_flat_query_tokens. Scoped tests escalated (justfile + core-identity after just install rebuilt sase-core) and were not run to completion.

[2026-08-19T16:26:56Z · sase-qv.5] Plain (non-plan) family roots now mirror a newest-shell monitor: running shows the start label + Running bucket; settled shows the stop label + the monitor bucket. copy_missing_display_metadata and _mirror_root_from_child copy monitor_start_status/monitor_stop_status/monitor_state so the container matches the monitor pair style; a later active follow-up clears the pair instead of leaving it stale. Verified 72 tests (monitor-family, followup/parallel/promoted-plan family, profile highlighting). Lint gates fmt/ruff/mypy/symvision/toobig passed. This phase has no leftover --epic-symbol entries. Re-keyed stale closed-bead Justfile lines sase-qt.6/* and sase-qt.7(MemoryPanel) to sase-qt. just check failed at init memory --check (feature spec digest); recorded as PROPOSED FOLLOW-UP.

[2026-08-19T16:30:54Z · sase-qv.5] Plain (non-plan) family roots now mirror a newest-shell monitor: running shows the start label + Running bucket; settled shows the stop label + the monitor bucket. copy_missing_display_metadata and _mirror_root_from_child copy monitor_start_status/monitor_stop_status/monitor_state so the container matches the monitor pair style; a later active follow-up clears the pair instead of leaving it stale. Verified 72 tests (monitor-family, followup/parallel/promoted-plan family, profile highlighting). Lint gates fmt/ruff/mypy/symvision/toobig passed. This phase has no leftover --epic-symbol entries. Re-keyed stale closed-bead Justfile lines sase-qt.6/* and sase-qt.7(MemoryPanel) to sase-qt. just check failed at init memory --check (feature spec digest); recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-qv.3](sase-qv.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qv.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qv.5/README.md) | [sase-qv.5](sase-qv.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`18dcf6b`](https://github.com/sase-org/sase/commit/18dcf6b8d5bd168884d55b916cba35b586473ef3) | feat(ace): mirror monitor status pairs onto family containers | [sase-qv.5](sase-qv.5.md) | 2026-08-19 12:35:36 EDT |
