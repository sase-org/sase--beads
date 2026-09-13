# Bead: sase-zn.9.4 — Integrate later refresh changes and resolve measured input hitches

[Bead Pages](../README.md) / [sase-zn.9](sase-zn.9.md) / sase-zn.9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zn.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.land.md) · **Assignee:** `sase-zn.9.4` · **Size:** medium
**Created:** 2026-09-12 17:29:05 EDT · **Closed:** 2026-09-13 10:57:46 EDT
**Plan:** [202609/finish\_ace\_typing\_lag.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_ace_typing_lag.md)

## Description

responsiveness: preserve deferred/indexed history and bounded reads, locate the remaining loop or pump delays, and produce fresh key-to-paint and benchmark evidence.

## Notes

[2026-09-13T11:32:07Z · sase-zn.9.4] PROPOSED FOLLOW-UP: Agents file-path hints still call get_workspace_directory, which runs git status on existing clones — 2026-09-13 tui_hitch on action t stacked in workspace_provider/_utils_checkout.py:ensure_git_clone_at from prompt_panel/_file_path_hints.py. Render path should only return already-materialized dirs.

[2026-09-13T11:32:09Z · sase-zn.9.4] PROPOSED FOLLOW-UP: Prompt-panel renderable digest hashes the full live-reply visual on j/k — 2026-09-13 tui_hitch/tui_pump_hitch stacks in ace/tui/util/renderable_digest.py and rich/text wrap while last_action=j. Cache the digest per visual generation instead of rehashing on every paint.

[2026-09-13T14:27:28Z · sase-zn.9.4] PROPOSED FOLLOW-UP: Existing ready task sase-lx still reproduces on the integrated tree — 2026-09-13 bounded slow bench reruns failed selected-tribe fold level 1 at next p95 58.03 ms / prev p95 46.78 ms with 260-282 ms max outliers after this phase fixed link-rail p95 delta; keep the existing sase-lx owner/context rather than creating a duplicate task.

[2026-09-13T14:57:01Z · sase-zn.9.4] PROPOSED FOLLOW-UP: Linked/published sase-core is behind Python expectations — `just check` full-suite escalation on 2026-09-13 failed monitor resume tests and LSP directive parity because `continuation_decide_resume_adoption` is absent from the available `sase_core_rs`/sase-core source and the rebuilt `sase-xprompt-lsp` lacks the `%queue` directive rows; `tools/probe_core_floor --advisory` reports `blocked_unpublished` for that binding.

[2026-09-13T14:57:46Z · sase-zn.9.4] Implemented render-path responsiveness fixes: file hints now resolve only existing workspaces, prompt panel reuses the update-time section digest, link rail skips identical recomposition, and unused monitor resume helper is private for Symvision. Verified: just fmt-py; just _lint-symvision; focused TUI/path tests passed (65 passed); link-rail slow bench rerun passed. Existing selected-tribe bench failure recorded against sase-lx. Ran just check: static/validation stages passed, then scoped lane escalated to full suite and failed in known core/LSP mismatch areas (missing continuation_decide_resume_adoption and stale %queue LSP rows); recorded PROPOSED FOLLOW-UP. epic-symbols had no entries.

## Dependencies

- **Depends on:** [sase-zn.9.1](sase-zn.9.1.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-zn.9.2](sase-zn.9.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zn.9.5](sase-zn.9.5.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.9.4/README.md) | [sase-zn.9.4](sase-zn.9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63e16c0`](https://github.com/sase-org/sase/commit/63e16c0fd2d84bd6c59edc4c2a09d6bc908de982) | fix(ace): reduce prompt panel render hitches | [sase-zn.9.4](sase-zn.9.4.md) | 2026-09-13 10:59:56 EDT |
