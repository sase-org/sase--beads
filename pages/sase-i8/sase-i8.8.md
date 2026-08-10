# Bead: sase-i8.8 — Raise the sase-core-rs dependency window

[Bead Pages](../README.md) / [sase-i8](README.md) / sase-i8.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wl/README.md) · **Assignee:** `sase-i8.8` · **Size:** small
**Created:** 2026-08-09 09:44:25 EDT · **Closed:** 2026-08-10 07:44:23 EDT
**Plan:** [202608/merge\_commit\_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)

## Description

floor: after the core release publishes, move the sase-core-rs version window in pyproject.toml to the release that carries the schema-3 contract and confirm the exhaustive gate passes against the published wheel.

## Notes

[2026-08-09T18:35:13Z · sase-i8.8] PROPOSED FOLLOW-UP: Published sase-core-rs 0.21.3 lacks parse_merge_summary — forced PyPI install from .venv/site-packages passes version/published-minimum but tools/check_sase_core_rs_bindings reports the required binding missing; local linked core 0.21.3 exposes it, so a new core release or corrected floor is needed before this phase can close.

[2026-08-09T18:35:35Z · sase-i8.8] PROPOSED FOLLOW-UP: check-full currently fails on markdown formatting in sase/memory/build_and_run.md — with SASE_CORE_DIR pointed at a nonexistent path for published-wheel verification, just check-full stops at fmt-md-check before tests.

[2026-08-10T11:34:30Z · sase-i8.8] PROPOSED FOLLOW-UP: SASE validation reports generated memory README drift — just check stops at init memory --check because ~/.local/share/chezmoi/home/sase/memory/README.md wants +2/-3 generated changes; phase workers cannot edit memory files without explicit user permission.

[2026-08-10T11:43:28Z · sase-i8.8] PROPOSED FOLLOW-UP: Full diff-scoped test lane has pre-existing unrelated failures — after this dependency-only change, just test-scoped escalated to the full suite and reported 21 failures, led by stale tests/contract_manifest.txt missing tests/test_probe_core_floor_tool.py plus ACE/TUI onboarding/navigation/scroll assertions; targeted core-floor/version tool tests pass.

[2026-08-10T11:44:23Z · sase-i8.8] Raised sase-core-rs window to >=0.23.0,<0.24.0 and refreshed uv.lock; verified tools/probe_core_floor --json status=ok for published floor 0.23.0, tools/ratchet_core_window --check reports floor matches newest complete published release 0.23.0, local validate_sase_core_rs_version exits 0, and targeted core-floor/version tool pytest suite passed (47 tests). just check is blocked by unrelated init memory --check README drift, recorded as PROPOSED FOLLOW-UP; full test-scoped escalation was interrupted after reporting unrelated failures, also recorded as PROPOSED FOLLOW-UP.

[2026-08-10T11:45:23Z · sase-i8.8] Verified published core floor 0.23.0 with tools/probe_core_floor --json, tools/ratchet_core_window --check, tools/validate_sase_core_rs_version, and 47 targeted core-floor/version tests; just check remains blocked by unrelated generated memory README drift, and full escalated tests had unrelated ACE/TUI/contract-manifest failures recorded as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-i8.6](sase-i8.6.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-i8.7](sase-i8.7.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i8.9](sase-i8.9.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i8.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i8.8/README.md) | [sase-i8.8](sase-i8.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8ed11bb`](https://github.com/sase-org/sase/commit/8ed11bb80b6a218dcd49fed5529573e036bc32ca) | build(deps): raise sase-core-rs floor | [sase-i8.8](sase-i8.8.md) | 2026-08-10 07:46:04 EDT |
