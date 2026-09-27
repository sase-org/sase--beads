# Bead: sase-1b6.3 — Switch the chezmoi epic and bd snippets

[Bead Pages](../README.md) / [sase-1b6](README.md) / sase-1b6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2a](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2a.md) · **Assignee:** `sase-1b6.3` · **Size:** xsmall
**Created:** 2026-09-27 08:18:57 EDT · **Closed:** 2026-09-27 10:24:38 EDT
**Plan:** [202609/snippet\_project\_variable.md](https://github.com/sase-org/sase--plans/blob/main/202609/snippet_project_variable.md)

## Description

chezmoi-epic-snippet: in the chezmoi repo's sase.yml, change the `epic` and `bd` snippets from the hard-coded sase- prefix to #{project}-, verify them with sase snippet show, and apply chezmoi after the commit lands.

## Notes

[2026-09-27T14:24:38Z · sase-1b6.3] epic/bd snippets use project-variable prefix; YAML values asserted, keep-sorted lint green, rep unchanged; snippet-show recheck + chezmoi apply at land

## Dependencies

- **Depends on:** [sase-1b6.2](sase-1b6.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1b6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1b6.3/README.md) | [sase-1b6.3](sase-1b6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@9b98c5c`](https://github.com/bbugyi200/dotfiles/commit/9b98c5c099843d350f0816fe4229cdb1d03b23a8) | feat(snippets): use #{project} prefix in epic and bd snippets | [sase-1b6.3](sase-1b6.3.md) | 2026-09-27 10:25:21 EDT |
