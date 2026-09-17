# Bead: sase-11y.2.1.5.1 — Correct service-status runtime scoping

[Bead Pages](../README.md) / [sase-11y.2.1.5](sase-11y.2.1.5.md) / sase-11y.2.1.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.1.land.md) · **Assignee:** `sase-11y.2.1.5.1` · **Size:** small
**Created:** 2026-09-17 19:38:47 EDT · **Closed:** 2026-09-17 19:52:53 EDT
**Plan:** [202609/complete\_service\_foundations\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/complete_service_foundations_landing.md)

## Description

status-runtime-scope: make sase-core honor the request boot id when projecting stops, deduplicate configured and orphan observations consistently, and add Rust and binding-level regressions.

## Notes

[2026-09-17T23:52:53Z · sase-11y.2.1.5.1] Verified status-runtime-scope in linked sase-core: cargo test -p sase_core service::status passed; cargo test -p sase_core_py service_status_bindings_round_trip_python_dicts passed; just check passed on rerun after transient gateway timeout tests passed exact reruns; epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-11y.2.1.5.2](sase-11y.2.1.5.2.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.2.1.5.1/README.md) | [sase-11y.2.1.5.1](sase-11y.2.1.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3c75d2e`](https://github.com/sase-org/sase-core/commit/3c75d2e6f5bdeb4fe7f88ef5ff542c524a61283e) | fix(service): scope service status stops by boot | [sase-11y.2.1.5.1](sase-11y.2.1.5.1.md) | 2026-09-17 19:54:03 EDT |
