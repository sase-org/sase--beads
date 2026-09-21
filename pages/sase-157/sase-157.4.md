# Bead: sase-157.4 — Gate the procfs process-identity token to Linux

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.4` · **Size:** medium
**Created:** 2026-09-21 06:25:47 EDT · **Closed:** 2026-09-21 08:55:57 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

sudo-identity: split process_identity_token so the procfs body is target_os = linux with an explicit unsupported-platform error elsewhere, add a config test seam so the detached handshake tests keep running off Linux, and make the macOS story for the sase_sudo_runner console script explicit.

## Notes

[2026-09-21T12:54:31Z · sase-157.4] PROPOSED FOLLOW-UP: sase_core telemetry::store::tests::concurrent_writers_preserve_every_delta flaked once under full-gate load then passed alone — detail: failed in ./scripts/check.sh all (3192 passed, 1 failed), passed on focused rerun; timing-sensitive concurrency test, unrelated to sudo-identity

[2026-09-21T12:55:57Z · sase-157.4] procfs body gated to target_os=linux with explicit unsupported-platform error elsewhere (mirrors host_liveness.rs); added process_identity_override seam honored by derive + handshake validation; handshake tests use synthetic token and Fixture forces detached path; new non-linux test pins error+empty capabilities (passes on mac arm64); mac run shows zero procfs/boot-id errors with remainder being the canonical-path defects owned by sase-157.5; Linux ./scripts/check.sh all green (3193+45 sudo_runner passed, fmt+clippy clean); audit confirms sudo_runner.rs is the only procfs reader in sase_gateway

## Dependencies

- **Depends on:** [sase-157.3](sase-157.3.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.5](sase-157.5.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.4/README.md) | [sase-157.4](sase-157.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b13332f`](https://github.com/sase-org/sase-core/commit/b13332f36e3ba924803ccde2a7084a1615a1e046) | feat(sase-core): gate procfs process-identity token to Linux | [sase-157.4](sase-157.4.md) | 2026-09-21 08:59:47 EDT |
