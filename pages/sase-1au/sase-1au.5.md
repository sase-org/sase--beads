# Bead: sase-1au.5 — Atomic entry-point rollout, documentation, and visual acceptance

[Bead Pages](../README.md) / [sase-1au](README.md) / sase-1au.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sy](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sy.md) · **Assignee:** `sase-1au.5` · **Size:** medium
**Created:** 2026-09-26 14:44:27 EDT · **Closed:** 2026-09-26 18:49:07 EDT
**Plan:** [202609/prompt\_recall\_tabs\_and\_stash\_trash.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_recall_tabs_and_stash_trash.md)

## Description

rollout_polish: route all shortcuts to the complete overlay and finish docs, glossary, visuals, and checks.

## Notes

[2026-09-26T22:48:43Z · sase-1au.5] PROPOSED FOLLOW-UP: scoped lane has 1 pre-existing failure unrelated to rollout — test_validate_proc_lifecycle_contract_passes_for_schema_v3_transitions expects proc-shell but installed core reports named-proc; fails identically on clean base tree (verified via stash). Symvision also reports 2 KNOWN findings in untouched files (main_view_blocks.py, legacy_sase_shell_syntax.py) with independent witnesses.

[2026-09-26T22:49:07Z · sase-1au.5] Rollout complete: @/,@/Ctrl+G p/chip/empty Ctrl+S open overlay on Stash, Ctrl+K/,./,> on History with live_bar/home_mru origins; bare-@ single-entry fast path kept; empty Stash opens overlay; Trash restore/purge with confirm+authoritative repaint; badge from active counts. Verified: 1252-test scoped selection green except 1 pre-existing proc failure (proven on clean tree, filed as follow-up); all lint gates pass except 2 KNOWN symvision in untouched files; prompt-stash goldens clean (5 unchanged); live wide (160x50) + narrow (90x30) overlay PNGs inspected; docs ace.md/configuration.md updated; Prompt Stash + Stash Trash glossary strands published.

## Dependencies

- **Depends on:** [sase-1au.4](sase-1au.4.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1au.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1au.5/README.md) | [sase-1au.5](sase-1au.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ade28c1`](https://github.com/sase-org/sase/commit/ade28c173a85e3bf520bb0947e1fb27e2ad3ba9b) | feat(ace): route all prompt entry points through Prompts overlay | [sase-1au.5](sase-1au.5.md) | 2026-09-26 19:06:21 EDT |
| sase | [`899bdba`](https://github.com/sase-org/sase/commit/899bdba6441eeaf7f27a303209b9d19a5d1ed89f) | feat(ace): route all prompt entry points through Prompts overlay | [sase-1au.5](sase-1au.5.md) | 2026-09-26 19:46:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1au.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1au.5/README.md

<!-- sase:referenced-by:end -->
