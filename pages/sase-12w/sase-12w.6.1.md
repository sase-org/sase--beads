# Bead: sase-12w.6.1 — Preserve executor ownership and stream command output

[Bead Pages](../README.md) / [sase-12w.6](sase-12w.6.md) / sase-12w.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12w.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.land.md) · **Assignee:** `sase-12w.6.1` · **Size:** large
**Created:** 2026-09-18 13:56:23 EDT · **Closed:** 2026-09-18 14:49:06 EDT
**Plan:** [202609/sudo\_detached\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_detached_landing_repairs.md)

## Description

runner: repair post-spawn failure ownership, provide live bounded output, and advertise only supported detach capabilities in sase-core.

## Notes

[2026-09-18T18:49:06Z · sase-12w.6.1--2] Implemented in sase-core sudo_runner: capability gating by identity backend, startup-ownership barrier (worker waits for matching started.json; post-spawn identity/publish failures reap the barred worker; final sudo -k failure still returns the handshake), concurrent live output draining with bounded ledger tails. Focused cargo test -p sase_gateway sudo_runner: 39 passed. cargo clippy -p sase_gateway --all-targets -D warnings passed. rustfmt applied. sase-core just check passed. Wait-keyword goldens updated to include hood after sase-11l.9. Primary SASE repo unmodified. sase bead epic-symbols sase-12w.6.1 empty.

## Dependencies

- **Blocks:** [sase-12w.6.2](sase-12w.6.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.6.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.6.1.md) | [sase-12w.6.1](sase-12w.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9bf272e`](https://github.com/sase-org/sase-core/commit/9bf272e832c85dc612a203a69d25458472e16165) | feat(sudo): preserve detached runner ownership and live output | [sase-12w.6.1](sase-12w.6.1.md) | 2026-09-18 14:51:03 EDT |
