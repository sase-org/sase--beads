# Bead: sase-1q4.2 — Rust wait-target vocabulary and pure rules

[Bead Pages](../README.md) / [sase-1q4](README.md) / sase-1q4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5j.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5j.linker.w0.md) · **Assignee:** `sase-1q4.2` · **Size:** medium
**Created:** 2026-10-30 17:43:13 EDT · **Closed:** 2026-10-30 21:28:12 EDT
**Plan:** [202610/fork\_wait\_session\_turn\_target.md](https://github.com/sase-org/sase--plans/blob/main/202610/fork_wait_session_turn_target.md)

## Description

vocab: add sase-core wait_target module (parse, effective-target rules, current-turn selection), the wait_target NamedEnum, pyo3 bindings, and a thin Python facade.

## Notes

[2026-10-31T00:16:48Z · sase-1q4.2] PROPOSED FOLLOW-UP: sase-1gz federation_worker listener_creates_private_socket_and_rejects_symlink flake under parallel sase-core check (passed alone)

[2026-10-31T01:27:44Z · sase-1q4.2] PROPOSED FOLLOW-UP: tests/llm_provider/test_claude_helper_guard.py::test_guard_p95_latency flake under loaded full-suite (p95 1.11s vs <1.0); passed isolation 0.57s

[2026-10-31T01:27:51Z · sase-1q4.2] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/decks/test_deck_view_main_pilot.py::test_reset_to_auto_matches_fresh_decision wait_for timeout under loaded full-suite; passed isolation

[2026-10-31T01:27:56Z · sase-1q4.2] PROPOSED FOLLOW-UP: tests/pager/test_app_navigation.py past_eof teardown AttributeError PagerScreen.notify after monkeypatch restore; unmodified pager tests, assertions pass, reproduces in isolation on this tree

[2026-10-31T01:28:12Z · sase-1q4.2] Landed wait_target vocab: sase-core parse/effective/select plus NamedEnum catalog, pyo3 bindings, Python facade, frontmatter catalog_choices for wait_target, macros.md type, and schema/docs. Symvision unused facade APIs re-keyed to sase-1q4.4/sase-1q4.5. sase just _lint-symvision green; sase tool run check 36a999e251b12a4bd9998cd06b24f614 lints/validation green, 59202 passed, 2 load flakes + 2 pre-existing pager teardown errors recorded as PROPOSED FOLLOW-UP. sase-core check only known flake sase-1gz (passed alone).

## Dependencies

- **Blocks:** [sase-1q4.4](sase-1q4.4.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q4.2/README.md) | [sase-1q4.2](sase-1q4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d7b00dd`](https://github.com/sase-org/sase-core/commit/d7b00dd7e2088d64a4cf335385856c17d44a3bed) | feat(wait\_target): add parse, effective-target, and NamedEnum vocabulary | [sase-1q4.2](sase-1q4.2.md) | 2026-10-30 21:29:22 EDT |
