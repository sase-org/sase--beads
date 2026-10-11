# Bead: sase-1jx.3 — sase-core candidate classification and creation-form evaluation

[Bead Pages](../README.md) / [sase-1jx](README.md) / sase-1jx.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.49.linker.w1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.49.linker.w1.md) · **Assignee:** `sase-1jx.3` · **Size:** medium
**Created:** 2026-10-11 11:13:45 EDT · **Closed:** 2026-10-11 13:06:00 EDT
**Plan:** [202610/new\_project\_wizard.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard.md)

## Description

core-classify: add the sase-core `project_onboarding` module with `classify_project_candidates` and `evaluate_repo_creation_form`, their PyO3 bindings, table tests, a thin Python facade in sase, and the revision-pin bump.

## Notes

[2026-10-11T16:24:04Z · sase-1jx.3] PROPOSED FOLLOW-UP: sase-core check NEW failure is the known flake sase-1gz (federation_worker listener_creates_private_socket_and_rejects_symlink: unexpected error federation worker is already running for .../worker.sock); clippy/fmt/features passed and project_onboarding tests were green

[2026-10-11T17:05:44Z · sase-1jx.3] PROPOSED FOLLOW-UP: sase check KNOWN test_tui_app_import_stays_under_startup_budget (3516 modules vs 3513 cap) reproduces on merge-base with +0 from this phase; related flake sase-1ai tracks CPU not module count

[2026-10-11T17:06:00Z · sase-1jx.3] Verified: sase_core 28 project_onboarding tests and sase_core_py 4 binding tests pass; facade tests hide sidecar suffix, keep user -- names, and grey template excludes in lenient vs strict; REQUIRED_BINDINGS covers the three new symbols; sase-1jx.3 has no leftover --epic-symbol (facade symbols keyed to open sase-1jx.6/sase-1jx.8). sase-core check clippy/fmt/features green with 1 NEW that is known flake sase-1gz; sase check lint/mypy/symvision green with 1 KNOWN TUI import cap already 3516 on merge-base (+0 this phase). Host should auto-pin sase-core-revision.txt when both repos commit.

## Dependencies

- **Blocks:** [sase-1jx.4](sase-1jx.4.md) ◐ · ⧖ 2026-10-11
- **Blocks:** [sase-1jx.6](sase-1jx.6.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.3/README.md) | [sase-1jx.3](sase-1jx.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a169fb`](https://github.com/sase-org/sase/commit/1a169fb90904d78092ef31c6f00fe37947537142) | feat(core): add project\_onboarding facade for classify and form evaluation | [sase-1jx.3](sase-1jx.3.md) | 2026-10-11 14:05:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.3][1] | Need the phase scope and design file before verifying remaining work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.3/README.md

<!-- sase:referenced-by:end -->
