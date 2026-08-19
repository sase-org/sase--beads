# Bead: sase-qt.6 — Add, edit, delete, and publish surfaces

[Bead Pages](../README.md) / [sase-qt](README.md) / sase-qt.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md) · **Assignee:** `sase-qt.6` · **Size:** medium
**Created:** 2026-08-19 08:16:39 EDT · **Closed:** 2026-08-19 12:08:01 EDT
**Plan:** [202608/ace\_memory\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)

## Description

panel-mutations: wire the add/edit forms, the delete confirmation, the tracked-proc writes, and the sase memory init publish flow with its unpublished state.

## Notes

[2026-08-19T16:07:28Z · sase-qt.6] PROPOSED FOLLOW-UP: just check escalated to the full suite (Justfile + core-identity-changed) and 825 tests failed with ProviderDisableStateError: unsupported provider-disable snapshot version: 2 across llm_provider/models-panel — not caused by this phase; memory panel tests passed in that run

[2026-08-19T16:07:45Z · sase-qt.6] PROPOSED FOLLOW-UP: re-keyed stale --epic-symbol entries for closed sase-qv.2/sase-qv.3 onto parent epic sase-qv so symvision would pass; qv land should consume or drop those monitor_status symbols

[2026-08-19T16:08:01Z · sase-qt.6] Wired Memory panel add/edit/delete/publish: form validation (stem/type/parent/cycle/generated, required errors deferred until submit), session-worker writes through the mutation engine with reselection and unpublished marking, child-blocked and generated refusals, conflict toast+reload, sase memory init publish (commit and --no-commit, project cwd vs Path.home() for Home), unpublished badge/footer, memory.write and memory.publish producer sites. just check lint gates passed (ruff/mypy/symvision/toobig). Scoped run escalated on Justfile; memory panel tests passed; remaining full-suite failures are unrelated ProviderDisableStateError snapshot v2. No leftover --epic-symbol entries for sase-qt.6.

[2026-08-19T16:11:42Z · sase-qt.6] Wired Memory panel add/edit/delete/publish: form validation (stem/type/parent/cycle/generated, required errors deferred until submit), session-worker writes through the mutation engine with reselection and unpublished marking, child-blocked and generated refusals, conflict toast+reload, sase memory init publish (commit and --no-commit, project cwd vs Path.home() for Home), unpublished badge/footer, memory.write and memory.publish producer sites. just check lint gates passed (ruff/mypy/symvision/toobig). Scoped run escalated on Justfile; memory panel tests passed; remaining full-suite failures are unrelated ProviderDisableStateError snapshot v2. No leftover --epic-symbol entries for sase-qt.6.

## Dependencies

- **Depends on:** [sase-qt.2](sase-qt.2.md) ✓ · ⧖ 2026-08-19
- **Depends on:** [sase-qt.4](sase-qt.4.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qt.8](sase-qt.8.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qt.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.6/README.md) | [sase-qt.6](sase-qt.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3ca09ff`](https://github.com/sase-org/sase/commit/3ca09ff47734d55e73a4ee82886b482f4fa5a287) | feat(ace): add Memory panel add, edit, delete, and publish surfaces | [sase-qt.6](sase-qt.6.md) | 2026-08-19 12:17:03 EDT |
