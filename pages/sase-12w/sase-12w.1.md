# Bead: sase-12w.1 — Runner auth-then-spawn mode and handshake wire

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.1` · **Size:** large
**Created:** 2026-09-18 08:50:38 EDT · **Closed:** 2026-09-18 09:32:54 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

runner: teach sase_sudo_runner (sase-core) a detach mode that authenticates on the TTY, spawns a detached root executor for the sealed manifest, invalidates the sudo timestamp, and prints a started-handshake; add the handshake wire type, a --capabilities probe, and sase_core_py bindings.

## Notes

[2026-09-18T13:32:54Z · sase-12w.1] Implemented detached sudo runner execution and validated with: cargo fmt; cargo test -p sase_core sudo::tests::exec_started -- --nocapture; cargo test -p sase_gateway sudo_runner::tests -- --nocapture; cargo test -p sase_core sudo::tests -- --nocapture; cargo test -p sase_core_py sudo_bindings_validate_manifest_risk_ledger_and_help -- --nocapture; cargo test -p sase_core_py gateway_and_bootstrap_bindings_are_registered -- --nocapture; cargo test -p sase_xprompt_lsp server::tests::wait_completion_uses_kind_aware_agent_catalog -- --nocapture; just check; sase bead epic-symbols sase-12w.1.

## Dependencies

- **Blocks:** [sase-12w.2](sase-12w.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.1.md) | [sase-12w.1](sase-12w.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b70e64d`](https://github.com/sase-org/sase-core/commit/b70e64d84902e5638dee62cb1512d0d853418747) | feat(sudo): add detached runner execution | [sase-12w.1](sase-12w.1.md) | 2026-09-18 09:36:13 EDT |
