# Bead: sase-16n.10 — Docs, skills, memory, config, and machine verification

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.10` · **Size:** medium
**Created:** 2026-09-22 18:48:55 EDT · **Closed:** 2026-09-23 08:08:26 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

docs-memory: docs and CLI help move to +<project>; fix the sase_run skill example; add the Project Tag glossary strand and update the sase-project and xprompts notes; drop redundant chezmoi gh_* xprompt shortcuts; run the final doctor verification on this machine.

## Notes

[2026-09-23T12:08:26Z · sase-16n.10] Docs-memory done: guides/CLI help/skill present +<project> as default (Patch/owner-repo/@agent/new-project stay #gh:/#git:); new glossary Project Tag strand, sase-project + xprompts notes updated, memory init republished; chezmoi gh_dotfiles/gh_sase removed (yaml valid). Verified: doctor project.name_collisions OK, project list TAG column shows +tags, +sase->#gh:gh_sase-org__sase / +Sase casefold / +home->#git:home, anchored +ssae raises with suggestions; sase tool run check green. Schema untouched (its #gh: descriptions cover namespace completion, intentionally unchanged per D9). sase xprompt expand CLI path blocked by sibling live claim on workspace 18, verified at function level instead.

## Dependencies

- **Depends on:** [sase-16n.2](sase-16n.2.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.5](sase-16n.5.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.7](sase-16n.7.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.8](sase-16n.8.md) ✓ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.9](sase-16n.9.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.10/README.md) | [sase-16n.10](sase-16n.10.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9f9c2b7`](https://github.com/sase-org/sase/commit/9f9c2b702733359d4af16f4fdb662df50f9ebdb1) | docs(project-tags): present +\<project\> tags as the default project spelling | [sase-16n.10](sase-16n.10.md) | 2026-09-23 08:10:00 EDT |
| chezmoi | [`chezmoi@996c65b`](https://github.com/bbugyi200/dotfiles/commit/996c65b04738ae934b1a67e14011167232021337) | chore(xprompts): drop redundant gh\_dotfiles and gh\_sase shortcuts | [sase-16n.10](sase-16n.10.md) | 2026-09-23 08:11:34 EDT |
