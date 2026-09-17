# Bead: sase-11y.2.1.4 — Enablement resolution and the service status snapshot wire

[Bead Pages](../README.md) / [sase-11y.2.1](sase-11y.2.1.md) / sase-11y.2.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.4` · **Size:** medium
**Created:** 2026-09-16 15:15:29 EDT · **Closed:** 2026-09-17 16:36:32 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

## Description

status-wire: add enablement-provenance resolution, the schema-versioned service status snapshot (pure state derivation plus a change token that ignores heartbeat churn), and atomic snapshot read/write in sase-core with bindings, plus the `sase.service.status` Python facade.

## Notes

[2026-09-17T18:38:53Z · sase-11y.2.1.4] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past status-wire core commit — new status-wire bindings and the Python facade require the land step to advance the pinned core revision after the core commit exists

[2026-09-17T20:36:32Z · sase-11y.2.1.4] Implemented service status wire/facade and verified with cargo test -p sase_core service::status --lib; cargo test -p sase_core_py service_status_bindings_round_trip_python_dicts; core just check; just install; just fix; pytest tests/service/test_service_status.py; clean default just test-scoped; plus just check static stages through committed plans.

## Dependencies

- **Depends on:** [sase-11y.2.1.3](sase-11y.2.1.3.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.2.1.4/README.md) | [sase-11y.2.1.4](sase-11y.2.1.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`05c6094`](https://github.com/sase-org/sase/commit/05c6094b80894b3f9623d20c5259900835c732b6) | feat(service): add status snapshot facade | [sase-11y.2.1.4](sase-11y.2.1.4.md) | 2026-09-17 19:22:40 EDT |
| sase-core | [`sase-core@fe7c4a0`](https://github.com/sase-org/sase-core/commit/fe7c4a0e6c555af3100c9c7463b7e982ec2cfa4f) | feat(service): add status snapshot wire | [sase-11y.2.1.4](sase-11y.2.1.4.md) | 2026-09-17 19:24:46 EDT |
