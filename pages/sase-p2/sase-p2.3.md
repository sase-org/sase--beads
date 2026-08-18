# Bead: sase-p2.3 — K opens the repo card

[Bead Pages](../README.md) / [sase-p2](README.md) / sase-p2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.059](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.059.md) · **Assignee:** `sase-p2.3` · **Size:** medium
**Created:** 2026-08-17 18:09:17 EDT · **Closed:** 2026-08-17 22:00:08 EDT
**Plan:** [202608/prompt\_repo\_mentions.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_repo_mentions.md)

## Description

preview: add the repo preview card `K` opens for the mention under the cursor, with kind/description/checkout/clone/remote/declaration detail and copy, edit, and view actions.

## Notes

[2026-08-18T01:38:43Z · sase-p2.3--4] PROPOSED FOLLOW-UP: Justfile --epic-symbol entries for GlossaryProjectRef/GlossaryProjectSnapshot/build_glossary_project_ring/load_glossary_project_snapshot were re-keyed from the closed sase-p1.4 to the parent epic sase-p1 (unrelated glossary-panel epic, not sase-p2.3 work) because just check went red for this repo when sase-p1.4 closed mid-session. Whichever sase-p1 phase (p1.5-p1.8) actually wires these symbols into the glossary panel should re-key the entry to itself or drop it once it has a real consumer.

[2026-08-18T02:00:08Z · sase-p2.3--5] Added RepoPreviewModal/repo_preview_render for the K repo-card preview and lavender repo-name links in the prompt (_prompt_preview.py, _prompt_repo_mentions.py, repo_mention_catalog.py). Fixed symvision fallout: removed 6 stale sase-p1.6 epic-symbol entries (already properly used), made repo_declaration_display private (only used within its own file), and re-keyed 4 stale sase-p1.4 epic-symbol entries to parent epic sase-p1 (symbols still await consumption by later in-progress phases; PROPOSED FOLLOW-UP note recorded). Updated the K-warning test to match the new repo-name wording. just check passed clean: fmt, all lint gates (including symvision), SASE validation, committed plans, and the full test suite (32656 passed, 13 skipped) after scoped selection escalated due to Justfile changes. sase bead epic-symbols sase-p2.3 confirms no leftover --epic-symbol entries for this bead.

[2026-08-18T02:00:52Z · sase-p2.3--5] Verified: just check passed clean (all lint gates including symvision, SASE validation, committed plans; full test suite 32656 passed, 13 skipped). Confirmed no --epic-symbol leftovers remain for sase-p2.3 via sase bead epic-symbols.

## Dependencies

- **Depends on:** [sase-p2.2](sase-p2.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p2.4](sase-p2.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p2.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p2.3.md) | [sase-p2.3](sase-p2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f54a911`](https://github.com/sase-org/sase/commit/f54a911753be1eed4a6576f4a14fdde7389940fe) | feat(ace): add K repo preview card for mentioned repos | [sase-p2.3](sase-p2.3.md) | 2026-08-17 22:03:01 EDT |
