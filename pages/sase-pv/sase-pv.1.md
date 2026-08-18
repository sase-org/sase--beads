# Bead: sase-pv.1 — Free the \`flag\` task-type slug

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.1` · **Size:** small
**Created:** 2026-08-18 11:26:03 EDT · **Closed:** 2026-08-18 12:22:52 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

slug: drop `flag` from the Rust core's reserved task-type slug list so a project may claim it, leaving the issue type untouched.

## Notes

[2026-08-18T15:53:57Z · sase-pv.1--1] Re-keyed Justfile --epic-symbol entries from closed sase-pq.5 to still-open parent epic sase-pq (TaskTypeGateDisplay and six helpers still have no non-test consumer). just _lint-symvision now passes. Reserved-slug work is already implemented in sase-core + Python test; re-running just check-full.

[2026-08-18T16:22:52Z · sase-pv.1--2] Dropped flag from RESERVED_TASK_TYPE_SLUGS (now plan/phase/task + untyped/unknown/all/none). Rust accepts_flag_as_a_claimable_task_type_slug and Python test_validate_task_type_spec_accepts_flag_slug pass; Flag issue type / FlagRecord / BeadFlagWire left untouched. sase-core just check and this repo just check-full passed (monitor c5ggnnpjwxkj, exit 0). sase bead epic-symbols sase-pv.1 reported no leftovers. Unrelated stale sase-pq.5 --epic-symbol lines were re-keyed to still-open parent sase-pq so check-full could pass.

[2026-08-18T16:24:12Z · sase-pv.1--2] Reserved-slug change verified: sase-core dropped flag from RESERVED_TASK_TYPE_SLUGS (now plan/phase/task plus untyped/unknown/all/none); Rust accepts_flag_as_a_claimable_task_type_slug and Python test_validate_task_type_spec_accepts_flag_slug pass; flag issue type untouched; just install, sase-core just check, and just check-full passed (monitor c5ggnnpjwxkj). Stale sase-pq.5 --epic-symbol lines re-keyed to still-open parent sase-pq so verification could pass.

## Dependencies

- **Blocks:** [sase-pv.2](sase-pv.2.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pv.1.md) | [sase-pv.1](sase-pv.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3f4e773`](https://github.com/sase-org/sase-core/commit/3f4e7733703454904a15848a33298713591895e6) | feat(task\_type): drop flag from reserved task-type slugs | [sase-pv.1](sase-pv.1.md) | 2026-08-18 12:25:44 EDT |
