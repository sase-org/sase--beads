# Bead: sase-1kx.1 — Fix the Master Gate test reds at master HEAD

[Bead Pages](../README.md) / [sase-1kx](README.md) / sase-1kx.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10b.md) · **Assignee:** `sase-1kx.1` · **Size:** medium
**Created:** 2026-10-14 07:18:03 EDT · **Closed:** 2026-10-14 08:47:47 EDT
**Plan:** [202610/v0\_18\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1ky][1] | Archive expand flake proposed by the release gate phase after timeboxed stress failed to reproduce it |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1ky/README.md

<!-- sase:links:end -->

## Description

gate-reds: delete the stale _RunManifest import, fix the lazy-export monkeypatch pollution that empties the bare-git provider registry, chase the archive-column flake, and fix every other deterministic red on the current tip.

## Notes

[2026-10-14T11:49:25Z · sase-1kx.1] PROPOSED FOLLOW-UP: Archive-column wait after `l` re-opens Today still a 3.13 Full CI flake (run 38530013190) — 20/20 serial and 3x `pytest -n 8` of tests/ace/tui/test_agent_archive_column_app.py passed locally; hypothesis: `_request_if_needed` stamps runtime.requested then assembles from a stale snapshot so a coalesced/dropped pump-free window request after expand never repaints `u.m@t00`. Timeout now includes selected_key, focused_section, folded_banners, controller generation/refreshing/status.

[2026-10-14T11:49:31Z · sase-1kx.1] PROPOSED FOLLOW-UP: tests/test_vcs_macro_mru_pruning.py::test_load_launchable_prunes_provider_mismatched_prefix fails identically on clean master (`#git:otherproj` pruned, got ["#gh:sase"]); likely the stale local sase_core_rs the epic already warns about, not this diff.

[2026-10-14T12:47:47Z · sase-1kx.1] gate-reds complete on 8e00f6d211.

_RunManifest import already deleted in 8e00f6d211; Master Gate 38555360266 shard 6 green at HEAD. test_conformance_warns_for_duplicate_root_and_leaked_helper_markers 20/20 serial; file 3x -n 8 green.

Lazy-export monkeypatch: shared _patch_workflow_metadata now patches the package facade before _registry; dual-patch call sites and only-registry metadata fakes now use it. _use_real_provider_registry pops the cached package global. Regression test_metadata_helper_restores_real_lazy_export_after_unresolved_package_global 20/20 serial (all three helpers) and 3x -n 8 of the file. Bare-git trio 20/20 each; reproducer pytest tests/history/test_prompt_canonical_text.py tests/project_onboarding/test_cli_bare_git.py 3x green. Newest Master Gate 38555360266 (SHA 8e00f6d211) failed only shard 8 (bare-git: []).

Archive-column: wait timeout now includes selected_key, focused_section, folded_banners, controller generation/refreshing/status. test_archive_replaces_the_inbox_column_and_keys_navigate_it 20/20 serial; file 3x -n 8 green. 3.13 Full CI flake (38530013190) not reproduced; PROPOSED FOLLOW-UP on this bead.

Re-inventory: no Full CI newer than 8847d07a08 (latest 38530013190 on 3cff3bea4f). Remaining reds there are visual-lane (sase-1kx.2), already-fixed-at-HEAD delivery_plan/_RunManifest, and the archive flake. sase-1ko did not land a delivery_plan expectation flip on this tip.

sase tool run check 22321509b16bc861ef7efed4cf0507bc green. tests/test_vcs_macro_mru_pruning.py::test_load_launchable_prunes_provider_mismatched_prefix fails identically on clean master; PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1kx.4](sase-1kx.4.md) ✓ · ⧖ 2026-10-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kx.1/README.md) | [sase-1kx.1](sase-1kx.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9f4e6c4`](https://github.com/sase-org/sase/commit/9f4e6c44309453eec4b43ed48192e778e5bece5d) | fix(tests): stop lazy-export patches emptying the git registry | [sase-1kx.1](sase-1kx.1.md) | 2026-10-14 08:49:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kx.1][1] | Need remaining notes, design, and remaining work after previous agent | 3 |
| read-by | [agent:sase-1kx.2--1][2] | See if Master Gate test reds already own these just-check failures | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kx.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.2.md

<!-- sase:referenced-by:end -->
