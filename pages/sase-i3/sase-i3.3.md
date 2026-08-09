# Bead: sase-i3.3 — Render display aliases and raise the core floor in sase

[Bead Pages](../README.md) / [sase-i3](README.md) / sase-i3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wa.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wa.f0/README.md) · **Assignee:** `sase-i3.3` · **Size:** medium
**Created:** 2026-08-09 08:18:16 EDT · **Closed:** 2026-08-09 09:13:39 EDT
**Plan:** [202608/glossary\_alias\_plurals.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_alias_plurals.md)

## Description

python: raise the sase-core-rs floor, carry the display alias list through the Python facade and LSP payload, render it in generated glossary memory, and regenerate the agent instruction files.

## Notes

[2026-08-09T13:11:19Z · sase-i3.3] PROPOSED FOLLOW-UP: File or fix new reproducible flake-baseline entries — just check-full reached ✓ test but selection-health reports tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_directory_key_spelling_also_resolves, tests/ace/tui/test_prompt_bar_xprompt_selector_requests.py::test_vcs_tag_offers_project_local_xprompts_by_canonical_name, and tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor as additions requiring a filed bead before landing.

[2026-08-09T13:13:39Z · sase-i3.3] Verified: just install; focused pytest for glossary memory/facade/LSP/prompt tests passed (27 passed); just test-visual passed (571 passed, 1 skipped); PATH=.venv/bin:[36m/home/bryan/.config/nvm/versions/node/v22.14.0/lib/node_modules/@openai/codex/node_modules/@openai/codex-linux-x64/vendor/x86_64-unknown-linux-musl/codex-path:/home/bryan/.config/nvm/versions/node/v22.14.0/bin:/home/bryan/.pyenv/plugins/pyenv-virtualenv/shims:/home/bryan/.pyenv/shims:/home/bryan/.pyenv/bin:/home/bryan/.cargo/bin:/home/bryan/.luarocks/bin:/home/bryan/projects/github/LuaLS/lua-language-server/bin:/home/bryan/.nix-profile/bin:/home/bryan/go/bin:/usr/local/go/bin:/home/bryan/.gems/bin:/home/bryan/.tmp/bin:/home/bryan/.flamegraph:/home/bryan/.dynamic-colors/bin:/home/bryan/bin:/home/bryan/.local/bin:/opt/rust-bin-1.97.1/bin:/home/bryan/.poetry/bin:/usr/local/bin:/sbin:/usr/sbin:/usr/share/safe-rm/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/snap/bin:/home/bryan/.fzf/bin[0m sase memory init --check passed; grep for ^Aliases: in generated instruction files returned no matches. just check-full passed lint/SASE validation/full pytest, then failed selection-health flake-baseline on three unrelated reproducible flakes; recorded PROPOSED FOLLOW-UP on this bead.

[2026-08-09T13:15:17Z · sase-i3.3] Clarification: the close note expanded $PATH in the shell; the intended verification command was PATH="$PWD/.venv/bin:$PATH" sase memory init --check, and it passed.

[2026-08-09T13:17:14Z · sase-i3.3] Verified just install; focused pytest; sase memory init --check; generated Aliases grep; just test-visual; just check-full reached full pytest pass and failed only selection-health on unrelated reproducible flakes recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-i3.2](sase-i3.2.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i3.3/README.md) | [sase-i3.3](sase-i3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b736093`](https://github.com/sase-org/sase/commit/b73609337d9bd1e7be6184bd4cd97f16cb342683) | feat(glossary): render core display aliases | [sase-i3.3](sase-i3.3.md) | 2026-08-09 09:20:30 EDT |
