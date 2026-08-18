# Bead: sase-p1.6 — Panel add and delete surfaces

[Bead Pages](../README.md) / [sase-p1](README.md) / sase-p1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.056](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.056.md) · **Assignee:** `sase-p1.6` · **Size:** medium
**Created:** 2026-08-17 17:42:40 EDT · **Closed:** 2026-08-17 22:38:38 EDT
**Plan:** [202608/glossary\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_panel.md)

## Description

actions: add the term-add form with live validation, the delete confirmation that shows the inbound blast radius, tracked-proc writes through the shared engine, the post-write commit offer, and the optimistic reselect-and-refresh behavior.

## Notes

[2026-08-18T02:08:23Z · sase-p1.6] PROPOSED FOLLOW-UP: re-keyed stale Justfile --epic-symbol sase-p2.3(RepoMention) to still-open sase-p2.4 after sase-p2.3 closed — p2.4/land should consume RepoMention or drop the whitelist entry

[2026-08-18T02:18:19Z · sase-p1.6--1] PROPOSED FOLLOW-UP: just check / sase validate fails doctor config.file_hooks when user-layer hook sase-research-artifacts@research-highlights is present but the linked plugin checkout is missing (editable pth points at empty src; ModuleNotFoundError) — sase repo open restored import and doctor went OK; validate should not require that host plugin for workspace gates, or just install should restore it

[2026-08-18T02:25:12Z · sase-p1.6--2] PROPOSED FOLLOW-UP: re-keyed stale Justfile --epic-symbol sase-p1.5(glossary_entry_relations) to still-open sase-p1.8 after sase-p1.5 closed — p1.8/land should consume glossary_entry_relations (travel chips) or drop the whitelist entry

[2026-08-18T02:38:38Z · sase-p1.6--3] Verified add form live Rust validation (ctrl+s submit, esc cancel) refuses invalid submit; delete confirmation lists inbound REFERENCED BY blast radius with default Cancel; writes go through app._submit_session_worker calling add_glossary_term/delete_glossary_term off-thread via the shared engine; success invalidates catalog, reloads snapshot, reselects the new term or delete neighbor (including last-row delete), invalidates prompt glossary catalogs, and toasts (delete includes restore command + sase memory init); conflict toasts and refreshes; validation error leaves the file unchanged; config commit offer is built off the event loop. Re-keyed stale Justfile --epic-symbol sase-p2.3(RepoMention) to still-open sase-p2.4 and sase-p1.5(glossary_entry_relations) to still-open sase-p1.8 (did not consume the helper in delete confirmation because that would drop inbound names missing from the loaded catalog). just check passed (fmt, lint including symvision, SASE validation, committed plans, scoped tests escalated to full suite via justfile). sase bead epic-symbols sase-p1.6: no leftover --epic-symbol entries for this phase.

[2026-08-18T02:39:50Z · sase-p1.6--3] Add form live-validates via Rust and refuses submit on invalid input (ctrl+s submit, esc cancel). Delete confirmation lists inbound REFERENCED BY blast radius with default Cancel. Writes go through app._submit_session_worker calling add_glossary_term/delete_glossary_term off-thread on the shared engine. Success invalidates catalog, reloads snapshot, reselects the new term or delete neighbor (including last-row delete), invalidates prompt glossary catalogs, toasts (delete includes restore + sase memory init), and offers a config commit built off the event loop. Conflict toast+refresh; validation error leaves the file unchanged. Re-keyed stale Justfile --epic-symbol sase-p2.3(RepoMention) to sase-p2.4 and sase-p1.5(glossary_entry_relations) to sase-p1.8. just check passed (fmt, lint including symvision, SASE validation, committed plans, scoped tests escalated to full suite). sase bead epic-symbols sase-p1.6 reported no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-p1.1](sase-p1.1.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p1.4](sase-p1.4.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p1.7](sase-p1.7.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p1.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p1.6.md) | [sase-p1.6](sase-p1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`42f0db0`](https://github.com/sase-org/sase/commit/42f0db06debdf5d5ecc21e3e569c13c75f2cc28e) | feat(tui): add glossary panel add and delete surfaces | [sase-p1.6](sase-p1.6.md) | 2026-08-17 22:45:43 EDT |
