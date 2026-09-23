# Bead: sase-16n.5 — TUI prompt editor completion and tag defaults

[Bead Pages](../README.md) / [sase-16n](README.md) / sase-16n.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pl.md) · **Assignee:** `sase-16n.5` · **Size:** medium
**Created:** 2026-09-22 18:48:49 EDT · **Closed:** 2026-09-22 22:04:04 EDT
**Plan:** [202609/project\_tags.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags.md)

## Description

tui-editor: the + trigger through the core binding, in-place accept, accent-styled completion rows ordered current-project-first, tag prefills and MRU cycling, editor project context from tags, pre-submit tag validation, and shell completion for +.

## Notes

[2026-09-23T02:03:28Z · sase-16n.5] PROPOSED FOLLOW-UP: Repair pre-existing just-check red unrelated to tui-editor — symvision flags unused-public delete_paths_in_background in src/sase/_linked_repo_workspaces.py (identical at HEAD, untouched by this phase; noted by sase-16n.3/sase-16h.5/sase-169.5 before)

[2026-09-23T02:04:04Z · sase-16n.5] tui-editor done: trigger+accept via core project_tag_trigger/apply_selection (Python mirror + golden vectors deleted; goldens live in core project_tag/tests.rs); D7 rows (+name accent, dim provider detail, current badge; PR rows unchanged); tag prefills (picker, MRU head, quick-launch, clipboard, stack seeding, PMR origin, indicator tooltip) with cold-catalog # fallback; tag-aware MRU cycling/deletion; editor context via effective_* with warm-catalog gating; pre-submit D3 validation keeping draft on error; off-thread catalog warmup; shell + marker (bash/zsh/fish) backed by project_tag kind; cli_spec.json synced; vcs_project_completion PNG golden refreshed and inspected. Verified: 121 tag/vcs/cycling + 41 widget completion + 28 prefix/indicator + 149 completion/xprompt/context + 4721 widget-dir + 8418 TUI-top tests green; just check green except pre-existing symvision delete_paths_in_background (recorded as PROPOSED FOLLOW-UP). epic-symbols: none.

## Dependencies

- **Blocks:** [sase-16n.10](sase-16n.10.md) ◐ · ⧖ 2026-09-22
- **Depends on:** [sase-16n.3](sase-16n.3.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16n.6](sase-16n.6.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.5/README.md) | [sase-16n.5](sase-16n.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec5b91d`](https://github.com/sase-org/sase/commit/ec5b91d8dfe9956c3f738b367452efd7ca4a449c) | feat(xprompt): TUI prompt editor completion and tag defaults | [sase-16n.5](sase-16n.5.md) | 2026-09-22 22:05:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.5/README.md

<!-- sase:referenced-by:end -->
