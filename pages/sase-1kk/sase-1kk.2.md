# Bead: sase-1kk.2 — sase-core owns the dismissed-bundle archive index store

[Bead Pages](../README.md) / [sase-1kk](README.md) / sase-1kk.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.104](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.104.md) · **Assignee:** `sase-1kk.2` · **Size:** medium
**Created:** 2026-10-13 12:24:28 EDT · **Closed:** 2026-10-13 13:28:33 EDT
**Plan:** [202610/tui\_sigbus\_single\_sqlite\_owner.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_sigbus_single_sqlite_owner.md)

## Description

core-archive-store: port the dismissed-bundle index schema, writes, queries, rebuild, signature, and corrupt-file quarantine from Python into sase_core::agent_archive with PyO3 bindings and Rust tests.

## Notes

[2026-10-13T17:28:22Z · sase-1kk.2] PROPOSED FOLLOW-UP: sase_gateway ipc test listener_creates_private_socket_and_rejects_symlink fails under full parallel gate (stale worker.sock), passes alone; likely load flake, needs a sase-core flake bead triage

[2026-10-13T17:28:33Z · sase-1kk.2] sase-core owns dismissed-bundle archive index: new agent_archive::store (schema v3 byte-compatible DDL, upsert/delete/query/paths/visibility/identities/signature/rebuild+UTC-quarantine/progress), 9 PyO3 bindings registered+tested, mod.rs+corpus opens routed through store, payload hash reconciled to Python canonical JSON. Verified: 10 store tests, 37 agent_archive tests, 12 agent_custody binding tests, just fmt/fast/clippy clean; full gate green except unrelated sase_gateway socket flake (passes alone, recorded as follow-up). No CHANGELOG (release-plz owns it); verify wire unchanged (superset of Python fields); sase checkout untouched

## Dependencies

- **Blocks:** [sase-1kk.4](sase-1kk.4.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kk.2/README.md) | [sase-1kk.2](sase-1kk.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d30e133`](https://github.com/sase-org/sase-core/commit/d30e1337a848f0bef8978153de3731badee00d46) | feat(agent-archive): move dismissed-bundle archive index into sase\_core store | [sase-1kk.2](sase-1kk.2.md) | 2026-10-13 13:30:13 EDT |
