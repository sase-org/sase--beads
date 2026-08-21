# Bead: sase-rl.4 — Keymap migration, visual polish, documentation, and regression audit

[Bead Pages](../README.md) / [sase-rl](README.md) / sase-rl.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08v.md) · **Assignee:** `sase-rl.4` · **Size:** medium
**Created:** 2026-08-20 14:37:49 EDT · **Closed:** 2026-08-21 06:48:29 EDT
**Plan:** [202608/targeted\_mini\_xprompt.md](https://github.com/sase-org/sase--plans/blob/main/202608/targeted_mini_xprompt.md)

## Description

keymap_polish: complete the g-prefix migration, theme-safe presentation, documentation, snapshots, and end-to-end verification.

## Notes

[2026-08-21T10:47:37Z · sase-rl.4] PROPOSED FOLLOW-UP: patch/stitch terminology audit fails on existing changespec facade names - just check fails in src/sase/core/__init__.py and tests/test_lazy_facades.py on unclassified changespec tokens unrelated to mini-xprompt keymap work.

[2026-08-21T10:47:58Z · sase-rl.4] PROPOSED FOLLOW-UP: full ACE PNG visual suite has broad unrelated snapshot mismatches - the focused mini-xprompt visual file passes, but the attempted full visual run left 425 failure artifacts under .pytest_cache/sase-visual across unrelated snapshot modules.

[2026-08-21T10:48:29Z · sase-rl.4] Verified just install; focused keymap/widget/help tests passed (116); focused mini-xprompt visual snapshots passed (9); ran just check, which reached lint gates then failed on unrelated existing patch/stitch terminology audit in src/sase/core/__init__.py and tests/test_lazy_facades.py; epic-symbols reported no entries.

[2026-08-21T10:49:45Z · sase-rl.4] Verified: no epic-symbol entries; focused non-visual tests passed; focused mini-xprompt PNG visual tests passed; just check was run and failed only on unrelated existing terminology audit noted as follow-up.

## Dependencies

- **Depends on:** [sase-rl.3](sase-rl.3.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rl.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rl.4/README.md) | [sase-rl.4](sase-rl.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`996ebea`](https://github.com/sase-org/sase/commit/996ebeaa61e179d1693b5b0b991cdb8422a13fbe) | feat(ace)!: migrate prompt-local xprompt keymap | [sase-rl.4](sase-rl.4.md) | 2026-08-21 06:51:22 EDT |
