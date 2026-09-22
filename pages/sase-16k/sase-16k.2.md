# Bead: sase-16k.2 — Inert toggle\_agent\_header keymap plumbing

[Bead Pages](../README.md) / [sase-16k](README.md) / sase-16k.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pi](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pi.md) · **Assignee:** `sase-16k.2` · **Size:** small
**Created:** 2026-09-22 13:53:09 EDT · **Closed:** 2026-09-22 14:38:00 EDT
**Plan:** [202609/sticky\_agent\_header\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/sticky_agent_header_panel.md)

## Description

keymap: add the `toggle_agent_header` app action on `d` end to end (config, dataclass, registry shared-key pairs, binding, availability, palette entry, action), gated so it stays unavailable until the panel exists.

## Notes

[2026-09-22T18:24:23Z · sase-16k.2] PROPOSED FOLLOW-UP: just _lint-pyscripts fails on clean tree (tools/fix_tui_sdd Rule 2 closer-dir complaints); blocks just check

[2026-09-22T18:24:55Z · sase-16k.2] PROPOSED FOLLOW-UP: just _lint-symvision flags agent_env_refusal_reason in src/sase/service/platform.py on clean tree; blocks just check

[2026-09-22T18:36:35Z · sase-16k.2] PROPOSED FOLLOW-UP: pre-existing scoped-lane failures on clean tree (completion snapshot x2, test_shards drift, preview geometry); fail without keymap changes

[2026-09-22T18:37:08Z · sase-16k.2] PROPOSED FOLLOW-UP: lane-only flakes pass in isolation (plugins batch path, proc dispatch rebind); scoped-lane ordering suspected

[2026-09-22T18:38:00Z · sase-16k.2] toggle_agent_header on d end to end and inert: config, dataclass, registry pairs, binding, availability (False until panel adds header_toggle_available), action, palette entry gated hidden; docs + allowlist rows. Verified: new/extended keymap, command-availability, palette-catalog, and tab-scoping pilot tests pass; fmt/ruff/mypy/toobig and other runnable gates pass; PNG goldens untouched; epic-symbols clean. just check overall still blocked by pre-existing pyscripts/symvision failures proven identical on clean tree.

## Dependencies

- **Blocks:** [sase-16k.3](sase-16k.3.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16k.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16k.2/README.md) | [sase-16k.2](sase-16k.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9aa46d0`](https://github.com/sase-org/sase/commit/9aa46d006734b2fbbdf49ff2fc1074e209860775) | feat(agents): add inert toggle\_agent\_header keymap plumbing | [sase-16k.2](sase-16k.2.md) | 2026-09-22 14:39:49 EDT |
