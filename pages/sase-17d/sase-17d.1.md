# Bead: sase-17d.1 — LLM Calls stale-worker fix and split-key display

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qd](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0qd.md) · **Assignee:** `sase-17d.1` · **Size:** small
**Created:** 2026-09-23 19:16:47 EDT · **Closed:** 2026-09-23 19:34:53 EDT
**Plan:** [202609/agents\_tab\_decks\_and\_cards.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_decks_and_cards.md)

## Description

llm-calls-subject-guard: stop LLM Calls worker results from painting onto a different agent, and teach key validation and display about backslash and vertical_line so split keys can be overridden and shown.

## Notes

[2026-09-23T23:34:20Z · sase-17d.1] PROPOSED FOLLOW-UP: symvision gate fails on clean tree for plugins_browser_install split modules importing private _CombinedInstallOutcome/_combined_install_message/_install_many_skipped_message/_source_variant_label — blocks just check for all agents

[2026-09-23T23:34:53Z · sase-17d.1] Stale-worker subject guard + split-key display done. Verified: 181 tests pass (new subject-guard suite incl. select-B-while-A-in-flight flow, keymaps validation/defaults/app-bindings, command catalog, llm panel cache/timeline). just check via sase tool run fails only on pre-existing symvision violation in plugins_browser_install split modules, confirmed identical on clean tree; filed as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-17d.3](sase-17d.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.1/README.md) | [sase-17d.1](sase-17d.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c701d6`](https://github.com/sase-org/sase/commit/9c701d658fef3edcef2981da5c09058ae0844ad1) | fix(tui): guard LLM Calls panel against stale-worker paints; split-key display | [sase-17d.1](sase-17d.1.md) | 2026-09-23 19:36:21 EDT |
