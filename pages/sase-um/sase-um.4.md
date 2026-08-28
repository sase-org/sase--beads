# Bead: sase-um.4 — Throttle release-please to a schedule

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.4` · **Size:** medium
**Created:** 2026-08-26 19:12:26 EDT · **Closed:** 2026-08-26 19:47:55 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

## Description

throttle: move publish.yml's release-please and release-metadata reconciliation from every master push onto a schedule plus workflow_dispatch while keeping publishing prompt, closing the empty-rollup and generator-busy gate conditions.

## Notes

[2026-08-26T23:37:16Z · sase-um.4] PROPOSED FOLLOW-UP: make rust-lsp-install honor configured cargo target and fail on copy errors — just install built sase-xprompt-lsp under /mnt/poseidon/cargo-target/release, tried to copy from the checkout-local target, printed cp/chmod/mv failures, and still exited 0.

[2026-08-26T23:47:55Z · sase-um.4] Verified publish.yml no longer has a push trigger; release-please and sync-release-metadata are schedule/workflow_dispatch-only while publish_existing dispatch still gates build/publish. Ran .venv/bin/python -m pytest tests/test_github_actions_ci.py -k publish and just check; ran sase bead epic-symbols sase-um.4 with no entries.

## Dependencies

- **Blocks:** [sase-um.8](sase-um.8.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.4/README.md) | [sase-um.4](sase-um.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bee0592`](https://github.com/sase-org/sase/commit/bee05929dd7104804fd9d13252da1789fcd6e2bb) | ci(release): throttle release-please workflow | [sase-um.4](sase-um.4.md) | 2026-08-26 19:49:15 EDT |
