# Bead: sase-1ig.11 — Document the three commands and record the human-only rule

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.11` · **Size:** small
**Created:** 2026-10-08 18:23:32 EDT · **Closed:** 2026-10-09 01:55:55 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

install-docs: add INSTALL.md's checkout section, a your-sase-versus-the-checkout's-venv guide in docs/development.md, README/CONTRIBUTING pointers, and the new `global-install-is-human-only` decisions strand.

## Notes

[2026-10-09T05:55:46Z · sase-1ig.11] PROPOSED FOLLOW-UP: just check lint (test waits) fails on tests/ace/tui/test_plan_decision_ace_stale.py:183,310 inline-pause-wait (file and tools/check_test_wait_helpers untouched by this phase; pre-existing)

[2026-10-09T05:55:55Z · sase-1ig.11] Docs phase done: INSTALL.md gained Installing-from-a-checkout section (3-command table, cargo/SASE_CORE_DIR prereqs, sase-update relation, human-only rule); docs/development.md gained Your-sase-versus-this-checkouts-.venv subsection (install-dev vs install-venv, agent guard + SASE_GLOBAL_INSTALL_BYPASS via /sase_gate); README/CONTRIBUTING/docs-rust_backend point at it; new decisions strand global-install-is-human-only registered via sase memory init and renders. Verified: just install-dev --help/-n guard text matches docs; sase tool run check passes fmt(markdown/python/generated-docs) and lint through mypy/flags/pyscripts; lint(test-waits) failure on untouched test_plan_decision_ace_stale.py recorded as PROPOSED FOLLOW-UP; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1ig.8](sase-1ig.8.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.11/README.md) | [sase-1ig.11](sase-1ig.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29724dc`](https://github.com/sase-org/sase/commit/29724dc042f4f8ad8ea0775448ab3e22f1d29c9f) | docs(install): document the three install commands and record the human-only rule | [sase-1ig.11](sase-1ig.11.md) | 2026-10-09 01:57:51 EDT |
