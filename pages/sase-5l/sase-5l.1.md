# Bead: sase-5l.1 — doctor: add llm.auth offline provider auth-evidence check

[Bead Pages](../README.md) / [sase-5l](README.md) / sase-5l.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5l.1`
**Created:** 2026-07-08 05:09:50 UTC
**Plan:** [sdd/plans/202607/sase\_doctor\_diagnostics.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202607/sase_doctor_diagnostics.md)

## Description

Add a default, offline-only llm.auth diagnostic to sase doctor (register in src/sase/doctor/runner.py). OK when the selected provider CLI is present and local credential evidence or a relevant API-key env var exists; WARN when the CLI is present but no local auth evidence is found; SKIP when llm.default already reports the CLI missing. Drive it from provider-declared credential-path and API-key-env metadata (add registry/hook metadata; reuse _PROVIDER_SETUP_HINTS), never an if-provider ladder. Keep auth_verified false unless a provider-owned bounded status command can verify without an LLM call, quota use, or interactive login. Add focused tests. See research section 1 and the epic plan design file.

## Notes

COMMIT: 265b6b779

[2026-07-27T21:39:23Z · sase-a1.land] [2026-07-08T05:48:39Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented default offline llm.auth doctor check backed by provider-declared auth evidence metadata; added registry/provider metadata and focused tests. Verified with just check.

## Dependencies

- **Blocks:** [sase-5l.2](sase-5l.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5l.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5l.1/README.md) | [sase-5l.1](sase-5l.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`141fcbe`](https://github.com/sase-org/sase/commit/141fcbe29e53f077970a72b2fd234227fe6c2f7e) | feat(doctor): add offline LLM auth evidence check (sase-5l.1) | [sase-5l.1](sase-5l.1.md) | 2026-07-08 05:52:58 |
