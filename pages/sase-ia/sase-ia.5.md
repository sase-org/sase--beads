# Bead: sase-ia.5 — Migrate downstream repository configs

[Bead Pages](../README.md) / [sase-ia](README.md) / sase-ia.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.we.f0.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.we.f0.w1/README.md) · **Assignee:** `sase-ia.5` · **Size:** small
**Created:** 2026-08-09 10:23:57 EDT · **Closed:** 2026-08-09 11:18:48 EDT
**Plan:** [202608/memory\_config\_section.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_config_section.md)

## Description

downstream-repos: migrate the bob-cli project config and the chezmoi user overlay to the nested form, correct the sase-nvim README reference, and confirm actstat needs no change.

## Notes

[2026-08-09T15:18:10Z · sase-ia.5] PROPOSED FOLLOW-UP: verify host sase is upgraded before merging the bob-cli config change — bob-cli/sase/sase.yml now declares memory.glossary with no legacy fallback key, and the globally-installed sase (currently 0.16.0+207.gd7e9ae8ae, older than this epic's read-sites fix) silently drops the entire glossary section with exit 0 when its post-commit sase memory init hook runs against that file, since old code only looks for a top-level glossary key. Reproduced directly: ran /home/bryan/.local/bin/sase memory init against the migrated bob-cli config and it regenerated CLAUDE.md/AGENTS.md/etc with the Glossary section deleted and no diagnostic. chezmoi is unaffected because only the chezmoi source file was edited, not the deployed ~/.config/sase copy, so the deployed legacy key keeps working until the user runs chezmoi apply. Land agent should confirm the host sase package is upgraded to include sase-ia.3 before/at the same time the bob-cli PR merges.

[2026-08-09T15:18:48Z · sase-ia.5] Migrated all four downstream repo configs per plan: (1) bob-cli sase/sase.yml — nested the Pomodoro/Schedule Log/Task Link glossary block under memory:, ran sase memory init with the workspace-local .venv/bin/sase (0.16.0+212.g3ec02513e, includes sase-ia.3's read-sites fix) and confirmed generated AGENTS.md/CLAUDE.md/GEMINI.md/OPENCODE.md/QWEN.md/sase/memory/README.md/sase/memory/glossary.md are byte-for-byte unchanged — only sase/sase.yml differs. (2) chezmoi home/dot_config/sase/sase_athena.yml — replaced amd_h1_title with nested memory.h1_title form; did not run chezmoi apply, that's the user's step, and the deployed ~/.config/sase copy keeps working via the legacy-key fallback until then. (3) sase-nvim README.md line 266 — updated the manual smoke-check step to reference memory.glossary instead of glossary; no Lua/syntax change needed. (4) actstat sase/sase.yml — re-confirmed via grep it declares neither glossary nor amd_h1_title; no change made. Filed a PROPOSED FOLLOW-UP about a deployment-timing risk discovered while verifying bob-cli: the globally-installed sase binary is older than this epic and silently drops the glossary section (exit 0, no diagnostic) when its post-commit hook runs memory init against the now nested-only bob-cli config.

[2026-08-09T15:19:57Z · sase-ia.5] Migrated glossary/h1_title config to nested memory.* keys across bob-cli (sase/sase.yml), chezmoi (home/dot_config/sase/sase_athena.yml), and sase-nvim (README.md manual smoke-check step). Verified in bob-cli via workspace-local sase build that regenerated CLAUDE.md/AGENTS.md and sase/memory/glossary.md are byte-for-byte unchanged after the migration. Confirmed actstat needs no change (declares neither legacy key).

## Dependencies

- **Depends on:** [sase-ia.2](sase-ia.2.md) ✓ · ⧖ 2026-08-09
- **Depends on:** [sase-ia.3](sase-ia.3.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ia.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ia.5/README.md) | [sase-ia.5](sase-ia.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@6a8d49c`](https://github.com/bbugyi200/dotfiles/commit/6a8d49c9f692280a2bd2c0abd45cf3ad5df8d465) | feat(config): nest amd\_h1\_title under memory.h1\_title in athena config | [sase-ia.5](sase-ia.5.md) | 2026-08-09 11:20:42 EDT |
| sase-nvim | [`sase-nvim@5c1b032`](https://github.com/sase-org/sase-nvim/commit/5c1b032ee9a3de772f50e8e0c7584368e65f3b6e) | docs: update glossary smoke-check to reference nested memory.glossary key | [sase-ia.5](sase-ia.5.md) | 2026-08-09 11:23:09 EDT |
