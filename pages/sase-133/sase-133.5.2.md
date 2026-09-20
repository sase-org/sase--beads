# Bead: sase-133.5.2 — Resolve production family presentation facts

[Bead Pages](../README.md) / [sase-133.5](sase-133.5.md) / sase-133.5.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-133.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.land.md) · **Assignee:** `sase-133.5.2` · **Size:** large
**Created:** 2026-09-19 08:06:11 EDT
**Plan:** [202609/remote\_parity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_parity_landing_repairs.md)

## Description

owner-facts: derive topology, rich statuses, tribe inheritance, shell facts, and runtime anchors from real owner records and consume them through the existing viewer renderer.

## Notes

[2026-09-20T12:15:21Z · sase-133.5.2] PROPOSED FOLLOW-UP: catalog reads artifact-directory timestamps as UTC — Rust parse_record_timestamp ignores the configured timezone, so rows lacking workflow_state.start_time show a start time offset by the host UTC offset

[2026-09-20T12:15:54Z · sase-133.5.2] PROPOSED FOLLOW-UP: master lint/test baseline failures unrelated to owner facts — mypy no-untyped-def in ace_tmux*.py, symvision private imports in memory/selector_models.py and main/ace_tmux_support.py, tests/test_capacity_gate_to_admission.py queue_weight

## Dependencies

- **Depends on:** [sase-133.5.1](sase-133.5.1.md) ✓ · ⧖ 2026-09-19
- **Blocks:** [sase-133.5.4](sase-133.5.4.md) ◐ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.5.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.5.2.md) | [sase-133.5.2](sase-133.5.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2631449`](https://github.com/sase-org/sase/commit/263144991496900af018d7470257dc841555d873) | feat(fleet): carry owner presentation facts through the viewer catalog adapter | [sase-133.5.2](sase-133.5.2.md) | 2026-09-20 08:17:33 EDT |
| sase-core | [`sase-core@92cf0ca`](https://github.com/sase-org/sase-core/commit/92cf0ca230a436a6dd48c9cd09aeb70759119404) | feat(fleet): derive owner presentation facts in core and bump contract to v5 | [sase-133.5.2](sase-133.5.2.md) | 2026-09-20 08:21:19 EDT |
