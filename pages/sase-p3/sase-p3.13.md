# Bead: sase-p3.13 — Make \`task\_type\` required end to end

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.13

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.13` · **Size:** small
**Created:** 2026-08-17 18:50:08 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

enforce: flip task creation to require a type in both the Rust core and the CLI once every teaching and rendering surface is in place.

## Notes

[2026-08-18T07:08:00Z · sase-p3.13] PROPOSED FOLLOW-UP: published sase-github still has no sase_task_types entry point — the external-mirror chop tests now fixture-isolate the github type, but a production mirror run still fail-closes with "required plugin sase-github is not installed" when the installed wheel does not export the type. Ship/require the sase-github version that registers github, or keep the catalog fixture as the test contract.

## Dependencies

- **Depends on:** [sase-p3.10](sase-p3.10.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.12](sase-p3.12.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.14](sase-p3.14.md) ◐ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.7](sase-p3.7.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.8](sase-p3.8.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.9](sase-p3.9.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.13](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.13/README.md) | [sase-p3.13](sase-p3.13.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@070a8a5`](https://github.com/sase-org/sase-core/commit/070a8a519d28a4d25a55bf6b4e83afdd1d09bb5a) | feat(bead)!: require an explicit task type on new task creation | [sase-p3.13](sase-p3.13.md) | 2026-08-18 02:32:46 EDT |
| sase | [`ab628ca`](https://github.com/sase-org/sase/commit/ab628ca7bf2c6156dcf90b6a1ac896e72e1febf3) | feat(bead)!: require a catalog task type on new task creation | [sase-p3.13](sase-p3.13.md) | 2026-08-18 03:08:39 EDT |
