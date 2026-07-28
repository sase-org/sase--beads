# Bead: sase-5l.6 — doctor: add integrations.mobile\_push\_config coherence check

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.6`
**Created:** 2026-07-08 05:11:52 UTC · **Closed:** 2026-07-08 20:25:32 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add a default integrations.mobile_push_config check that skips when push is disabled. SKIP when push disabled; OK for push_provider test, fcm_dry_run, or a complete FCM config; ERROR when fcm is selected but fcm_project_id or a credential source (service-account path or credential-env) is missing. Rationale: launch prep in src/sase/integrations/mobile_gateway.py appends FCM flags only when values are non-empty, so incoherent config passes through silently. Do NOT add any MCP diagnostic (MCP is not implemented in this repo). Add tests. See research section 6 and the epic plan design file.

## Dependencies

- **Depends on:** [sase-5l.5](sase-5l.5.md) ✓
- **Blocks:** [sase-5l.7](sase-5l.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.6/README.md) | [sase-5l.6](sase-5l.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`274a0ad`](https://github.com/sase-org/sase/commit/274a0ad8fc5461f356c5b748e28bbecfdfd81e2f) | feat(doctor): add mobile push config diagnostic (sase-5l.6) | [sase-5l.6](sase-5l.6.md) | 2026-07-08 07:05:51 |
