# Bead: sase-1le.20.1.16 — History and duplicate sweep for reference/tui/

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.16

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.16` · **Size:** medium
**Created:** 2026-10-16 08:04:39 EDT · **Closed:** 2026-10-16 16:59:45 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

tui-edit: strip history, bead IDs, and epic labels from the TUI reference pages into reference/upgrading/, replace keymap and registry restatements with generated links, and confirm template shape.

## Notes

[2026-10-16T20:20:41Z · sase-1le.20.1.16] Counts: history hits 101→52 on reference/tui/ and contribute/tui-rendering.md (kept current-feature "legacy" names, UI strings such as "no longer pending"/"no longer available", and "previously" as earlier-in-session). Replaced 2 hand-maintained CLI flag tables with generated-page links (sase tui, sase pager); linked generated screenshot/proc/final/agent-hold/patch-set-origin/tmux-agent/artifact CLI pages; added generated TUI keymaps links on agents-tab, files-and-preview, launch-control, procs-tab, projects-tab, and contribute/tui-rendering. All TUI pages keep opening sentence, Related, and description ≤160. Created docs/reference/upgrading/tui.md (command name, aliases, query tokens, prompt-history store, config/keymap aliases, in-process pager, detached procs, dismissed-name prefix, HITL/launch fallbacks, glossary lane, prompt-stack restore, session suffixes, Artifacts Agent pane, keymap moves, auto-name migration). 0 leftover --epic-symbol entries. just docs-lint passed (3 pre-existing contribute over-budget warnings). just docs-check passed (2776 URLs).

[2026-10-16T20:59:27Z · sase-1le.20.1.16--1] PROPOSED FOLLOW-UP: just check NEW failures reproduce on clean HEAD a9701c36e6 (docs stashed) — test_tui_app_import_stays_under_startup_budget 3520==3520 cap (sase-13p, sase-1ic); test_project_labels_never_derive_from_paths fails because repair_archived_prompt_path derives Path(project_file).parent.name (no existing bead; sase-1k4 tracks related header tests). Remaining sampled NEW nodes (axe chop bead_claim_checks, production oracles, dismiss persistence, new_project_configure_review) passed in isolation on that clean tree; they failed only in the loaded 13-worker full suite (touched=false).

[2026-10-16T20:59:45Z · sase-1le.20.1.16--1] Verified tui-edit: history/duplicate sweep on reference/tui/ and contribute/tui-rendering.md (counts in note #1), upgrading/tui.md added, 0 leftover --epic-symbol entries, template shape kept. just docs-lint and just docs-check passed earlier. just check (tool run f4dda85a7a858d2871d40cd975094377) failed 27 NEW tests; two reproduce identically on clean HEAD a9701c36e6 (import budget, project-label path audit) and the rest sampled passed in isolation — recorded as PROPOSED FOLLOW-UP. Did not close parent epic.

## Dependencies

- **Blocks:** [sase-1le.20.1.21](sase-1le.20.1.21.md) ◐ · ⧖ 2026-10-16
- **Depends on:** [sase-1le.20.1.6](sase-1le.20.1.6.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.16](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.1.16.md) | [sase-1le.20.1.16](sase-1le.20.1.16.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a00e034`](https://github.com/sase-org/sase/commit/a00e034d65cb22a9bedab32f15d7c8679a0de7c8) | docs(tui): sweep history into upgrading/tui and link generated pages | [sase-1le.20.1.16](sase-1le.20.1.16.md) | 2026-10-16 17:35:56 EDT |
| sase | [`f3087c8`](https://github.com/sase-org/sase/commit/f3087c86acbbd2e445a7a0054e3d596aafeeeb95) | docs: refresh instruction shims and pin duplicate sase-service heading | [sase-1le.20.1.16](sase-1le.20.1.16.md) | 2026-10-16 17:42:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.16--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.1.16.md

<!-- sase:referenced-by:end -->
