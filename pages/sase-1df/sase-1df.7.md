# Bead: sase-1df.7 — TUI Jinja completion menu redesign

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.7` · **Size:** medium
**Created:** 2026-09-30 08:47:28 EDT · **Closed:** 2026-09-30 14:09:02 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

tui-menu: drive the prompt input's Jinja menu from the engine, using each pane's frontmatter scope. Render aligned, theme-consistent rows with source badges, match highlighting, and a detail subtitle. Give Jinja precedence inside tags, and add dark/light PNG goldens.

## Notes

[2026-09-30T18:08:25Z · sase-1df.7] PROPOSED FOLLOW-UP: symvision check fails identically on the clean base tree (owner_ref in tool/owner.py plus phase-6 jinja_assist names and tool/ run-join debt; same list with my src/ stashed); see sase-1cx.4 which already tracks this symbol set

[2026-09-30T18:09:02Z · sase-1df.7] tui-menu done: engine-backed JinjaCompletionResult with scope/label plumbing, Jinja-first precedence in Ctrl+T/refresh/accept/claims, aligned theme-resolved rows with badges/fuzzy highlight/subtitle, slot titles + scope label, 15 pilot tests, 3 inspected PNG goldens; 167 widget tests green, lint gates green, symvision strictly improved vs base (remaining 19 items reproduce on clean tree, noted as follow-up)

## Dependencies

- **Depends on:** [sase-1df.6](sase-1df.6.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1df.8](sase-1df.8.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.7/README.md) | [sase-1df.7](sase-1df.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c6df2db`](https://github.com/sase-org/sase/commit/c6df2dba3f4211b0d71105a0cf6d30ebd54cfdaf) | feat(ace-tui): drive Jinja completion menu off Rust engine | [sase-1df.7](sase-1df.7.md) | 2026-09-30 14:12:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1df.7][1] | Need full description and design context | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.7/README.md

<!-- sase:referenced-by:end -->
