# Bead: sase-1kx.1 — Fix the Master Gate test reds at master HEAD

[Bead Pages](../README.md) / [sase-1kx](README.md) / sase-1kx.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10b.md) · **Assignee:** `sase-1kx.1` · **Size:** medium
**Created:** 2026-10-14 07:18:03 EDT
**Plan:** [202610/v0\_18\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release.md)

## Description

gate-reds: delete the stale _RunManifest import, fix the lazy-export monkeypatch pollution that empties the bare-git provider registry, chase the archive-column flake, and fix every other deterministic red on the current tip.

## Notes

[2026-10-14T11:49:25Z · sase-1kx.1] PROPOSED FOLLOW-UP: Archive-column wait after `l` re-opens Today still a 3.13 Full CI flake (run 38530013190) — 20/20 serial and 3x `pytest -n 8` of tests/ace/tui/test_agent_archive_column_app.py passed locally; hypothesis: `_request_if_needed` stamps runtime.requested then assembles from a stale snapshot so a coalesced/dropped pump-free window request after expand never repaints `u.m@t00`. Timeout now includes selected_key, focused_section, folded_banners, controller generation/refreshing/status.

[2026-10-14T11:49:31Z · sase-1kx.1] PROPOSED FOLLOW-UP: tests/test_vcs_macro_mru_pruning.py::test_load_launchable_prunes_provider_mismatched_prefix fails identically on clean master (`#git:otherproj` pruned, got ["#gh:sase"]); likely the stale local sase_core_rs the epic already warns about, not this diff.

## Dependencies

- **Blocks:** [sase-1kx.4](sase-1kx.4.md) ◐ · ⧖ 2026-10-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kx.1/README.md) | [sase-1kx.1](sase-1kx.1.md) | 0 |
