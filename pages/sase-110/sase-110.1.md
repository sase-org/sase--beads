# Bead: sase-110.1 — Sudo manifest contracts and the TTY-attached runner in sase-core

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.1` · **Size:** large
**Created:** 2026-09-14 11:33:14 EDT · **Closed:** 2026-09-14 12:45:29 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

core-runner: add the sudo manifest/ledger/risk-badge wire contracts to sase_core and an unprivileged sase_sudo_runner binary (sudo -v, per-command sudo -n, sudo -k on the controlling TTY) shipped as a wheel console script.

## Notes

[2026-09-14T16:45:29Z · sase-110.1] Implemented sudo manifest/ledger/risk-badge wire contracts, sase_sudo_runner, PyO3 bindings and wheel console script, mobile/fleet requires_tty deny-only remote approval, contract snapshots, docs, and CI/release smoke updates. Verified with focused sudo/mobile/fleet/gateway/PyO3 tests, PYO3_PYTHON=/usr/bin/python3 ./scripts/check.sh, and an isolated abi3 wheel install smoke running sase_sudo_runner --help.

## Dependencies

- **Blocks:** [sase-110.3](sase-110.3.md) ✓ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-110.1.md) | [sase-110.1](sase-110.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ab68522`](https://github.com/sase-org/sase-core/commit/ab68522ac465d11544d48d6881ad1ea0c9f372d3) | feat(sudo): add reviewed sudo runner contracts | [sase-110.1](sase-110.1.md) | 2026-09-14 12:47:27 EDT |
