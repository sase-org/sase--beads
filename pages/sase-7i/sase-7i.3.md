# Bead: sase-7i.3 — Release once-per keys for terminally failed launches

[Bead Pages](../README.md) / [sase-7i](README.md) / sase-7i.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7i.3`
**Created:** 2026-07-19 17:20:13 UTC
**Plan:** [202607/fix\_toobig\_split\_chop\_dedupe.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_toobig_split_chop_dedupe.md)

## Description

'Release once-per keys for terminally failed launches' section: record each launch's dedupe key in the durable launch descriptors and release keys through the new engine operation when the launch phase throws or when finalize_launched_chop_runs marks an agent's completion as failed.

## Notes

Implemented durable effective dedupe keys and artifact timestamps in launch descriptors; partial launch failures now retain successful launch keys and release only accepted unlaunched keys; terminal lifecycle failures match descriptors by artifact timestamp then PID, release only failed-agent keys, tolerate legacy missing keys, and log release errors without aborting finalization. Added regression coverage for partial launches, mixed success/failure, successful-key retention, follow-up re-acceptance, legacy descriptors, release-error logging, and incomplete linkage. Verification: 17 focused tests passed; formatting, Ruff, mypy, Symvision, SASE validation, and committed-plan validation passed. Full parallel just check reached 19295 passed with 3 unrelated tests that pass in isolation; one-worker run reached 18915 passed before unrelated process-state leakage caused an OSError cascade.

## Dependencies

- **Depends on:** [sase-7i.1](sase-7i.1.md) ✓
- **Blocks:** [sase-7i.5](sase-7i.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7i.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7i.3/README.md) | [sase-7i.3](sase-7i.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`fc6ef85`](https://github.com/sase-org/sase/commit/fc6ef851520ad59734daad458fa8c24b2dbfcb1a) | fix(axe): release once-per keys for failed chop launches (sase-7i.3) | [sase-7i.3](sase-7i.3.md) | 2026-07-19 18:55:58 |
