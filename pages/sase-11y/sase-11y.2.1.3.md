# Bead: sase-11y.2.1.3 — Restart decisions and the locked service state store

[Bead Pages](../README.md) / [sase-11y.2.1](sase-11y.2.1.md) / sase-11y.2.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.2.md) · **Assignee:** `sase-11y.2.1.3` · **Size:** medium
**Created:** 2026-09-16 15:15:28 EDT · **Closed:** 2026-09-17 11:38:07 EDT
**Plan:** [202609/core\_service\_foundations.md](https://github.com/sase-org/sase--plans/blob/main/202609/core_service_foundations.md)

## Description

restart-state: add the pure `decide_service_restart` function (restart policy, clean-exit rules, orchestrator-identical backoff and crash-loop accounting) and the flock-guarded `~/.sase/service/state.json` store (machine-local enablement overrides, boot-id-keyed stops, markers, host record) with bindings, plus the Python restart, state, paths, and boot-id facades.

## Notes

[2026-09-17T15:37:22Z · sase-11y.2.1.3] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past restart/state core commit - this phase intentionally did not edit the core pin; the land agent should ratchet after the host-owned core commit exists.

[2026-09-17T15:38:07Z · sase-11y.2.1.3] Implemented Rust service restart decisions/state store with PyO3 bindings plus Python facades/tests. Verified cargo test -p sase_core service::; cargo test -p sase_core_py service_; just install; focused service pytest; just fix; main just check; linked core just check with uv Python LD_LIBRARY_PATH; git diff --check in both repos; and sase bead epic-symbols sase-11y.2.1.3 reported no entries.

## Dependencies

- **Depends on:** [sase-11y.2.1.2](sase-11y.2.1.2.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.2.1.4](sase-11y.2.1.4.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.2.1.3/README.md) | [sase-11y.2.1.3](sase-11y.2.1.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13ea3da`](https://github.com/sase-org/sase/commit/13ea3da511e4c5673a41873be1f1ddaba08232ad) | feat(service): add restart and state facades | [sase-11y.2.1.3](sase-11y.2.1.3.md) | 2026-09-17 11:40:22 EDT |
| sase-core | [`sase-core@a756136`](https://github.com/sase-org/sase-core/commit/a756136bcf545eb5681236d22e818b731b693910) | feat(service): add restart and state core | [sase-11y.2.1.3](sase-11y.2.1.3.md) | 2026-09-17 11:41:27 EDT |
