# Bead: sase-kz.8 — Documentation and core version pin

[Bead Pages](../README.md) / [sase-kz](README.md) / sase-kz.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zm.md) · **Assignee:** `sase-kz.8` · **Size:** small
**Created:** 2026-08-13 12:29:12 EDT · **Closed:** 2026-08-13 15:50:30 EDT
**Plan:** [plans:202608/nested\_snippet\_sessions.md](https://github.com/sase-org/sase--plans/blob/main/202608/nested_snippet_sessions.md)

## Description

docs_pin: document nested sessions and backward navigation in the ACE and editor guides, update the keymap tables and CHANGELOG, and raise the sase-core-rs floor once the core release lands.

## Notes

[2026-08-13T19:47:53Z · sase-kz.8] PROPOSED FOLLOW-UP: resolve pre-existing Symvision failure for stream_and_parse_messages_json_output — just check reports the public helper in src/sase/llm_provider/_subprocess_claude.py as unused even though this phase only changed docs and dependency metadata.

[2026-08-13T19:50:30Z · sase-kz.8] Updated ACE/editor/config docs for nested snippet sessions and Shift+Tab retreat, raised sase-core-rs floor/lock to 0.26.10 after PyPI release. Verified: just install; just fmt-md-check; tools/validate_changelog; uv lock --check; importlib metadata reports sase-core-rs 0.26.10; pytest tests/ace/tui/widgets/test_prompt_snippet_expansion.py; just docs-check. just check reaches unrelated pre-existing Symvision failure for stream_and_parse_messages_json_output, recorded as PROPOSED FOLLOW-UP.

[2026-08-13T19:52:17Z · sase-kz.8] Verified docs and dependency floor updates with just install, just fmt-md-check, tools/validate_changelog, uv lock --check, package metadata for sase-core-rs 0.26.10, pytest tests/ace/tui/widgets/test_prompt_snippet_expansion.py, and just docs-check; full just check remains blocked by unrelated Symvision unused-symbol finding in src/sase/llm_provider/_subprocess_claude.py.

## Dependencies

- **Depends on:** [sase-kz.6](sase-kz.6.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-kz.7](sase-kz.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kz.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kz.8/README.md) | [sase-kz.8](sase-kz.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`026de34`](https://github.com/sase-org/sase/commit/026de34f6b312a8be4244281facc74b295791faf) | build(deps): require sase-core-rs 0.26.10 | [sase-kz.8](sase-kz.8.md) | 2026-08-13 15:53:18 EDT |
