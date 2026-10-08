# Bead: sase-1i5.5 — TUI macro-arg detection uses sase-core structural spans (sase-1h1)

[Bead Pages](../README.md) / [sase-1i5](README.md) / sase-1i5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0y8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0y8.md) · **Assignee:** `sase-1i5.5` · **Size:** medium
**Created:** 2026-10-08 09:47:20 EDT · **Closed:** 2026-10-08 11:55:27 EDT
**Plan:** [202610/close\_top\_ten\_impact\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/close_top_ten_impact_task_beads.md)

## Description

macro-arg-spans: replace raw comma and paren splitting in the TUI macro-arg detector with sase-core argument spans, add quoted-comma and quoted-paren golden fixtures in both repos, and close sase-1h1.

## Notes

[2026-10-08T14:46:24Z · sase-1i5.5] PROPOSED FOLLOW-UP: Python colon parser ignores quoted values — sase.macro._parsing parses #m:"a,b",staging as arg-less (ref end=2), so the choice-projection parity harness cannot re-bind colon-quoted applied edits; quoted-comma golden case ships without applied_edits

[2026-10-08T14:46:34Z · sase-1i5.5] PROPOSED FOLLOW-UP: TUI import budget still over cap on clean base (3582 vs 3570, identical with and without this phase) — owned by sase-13p via phase sase-1i5.8; this phase adds no eager imports

[2026-10-08T15:39:51Z · sase-1i5.5--1] PROPOSED FOLLOW-UP: sase check shows 2 NEW failures that reproduce identically on clean base (stashed 5 phase files, reran, both still fail): test_fast_path_refuses_mutation_from_plain_checkout_sidecar_record and test_default_list_includes_claimed_with_shared_glyph, both AttributeError _ReadView list_issue_page; unrelated to macro-arg-spans

[2026-10-08T15:52:58Z · sase-1i5.5--1] PROPOSED FOLLOW-UP: sase-core check red on clean base too — bead_read_parity event_store_supports_read_queries_without_legacy_projection fails identically with this phase stashed (pre-existing, unrelated to trigger_context quote fix)

[2026-10-08T15:55:27Z · sase-1i5.5--1] macro-arg-spans done: detection derives from sase-core macro_argument_spans (lazy loader, import count unchanged 3582), quoted-comma/paren goldens mirrored byte-identical both repos, sase-1h1 closed. sase check 7a71c18e: only failures base-identical pre-existing (2 NEW both fail on clean base + KNOWN lint/import-budget; follow-ups noted). sase-core check bb94c264: only failure base-identical pre-existing bead_read_parity test; area tests green (macro_arg 19, trigger_context 6, completion 154). epic-symbols clean. sase-core fix stays uncommitted in linked checkout; release phase sase-1i5.9 owns commit+pin (no new binding used, revision pin untouched).

## Dependencies

- **Blocks:** [sase-1i5.8](sase-1i5.8.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9](sase-1i5.9.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.5.md) | [sase-1i5.5](sase-1i5.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cd73d96`](https://github.com/sase-org/sase-core/commit/cd73d9687c3813915fc6db610236be9a6fd5eab6) | feat(macro): quote-aware paren close in completion trigger context | [sase-1i5.5](sase-1i5.5.md) | 2026-10-08 11:57:02 EDT |
