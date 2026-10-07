# Bead: sase-1h7.5 — Follow through in every release path

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.5` · **Size:** large
**Created:** 2026-10-06 18:17:39 EDT · **Closed:** 2026-10-07 15:36:44 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Previously Closed

> ↺ Closed 2026-10-07T15:12:19Z · done
>
> (none)
>
> Reopened 2026-10-07T16:05:04Z by a status update

## Description

release: route every release path (runner initial check, parked-runner fallback, AXE wait_checks chop, kill/dismiss) through one shared decision function. Promote FOLLOWING targets into pinned bead waits under the directive lock with compare-and-set, persist `wait_epic_follows`, fix the two-stage rewrite clobber, and document the opt-in keyword.

## Notes

[2026-10-07T15:05:48Z · sase-1h7.5--2] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py fails on clean base (module count 3570 == cap 3570; none of the sase-1h7.5 modules are in the TUI import closure). Environmental drift from the documented 3563 baseline; consider bumping _MAX_MODULE_COUNT.

[2026-10-07T15:12:00Z · sase-1h7.5--2] PROPOSED FOLLOW-UP: sase-core check fmt step fails on files this bead never touched (6 files incl. sase_macro_lsp completion.rs); current rustfmt wants to reformat the committed tree. Bead's 3 Rust files are rustfmt-clean, agent_scan lib tests 174 pass, clippy clean. Consider a repo-wide cargo fmt pass with the pinned toolchain.

[2026-10-07T15:12:19Z · sase-1h7.5--2] Release phase verified: fixed 2 NEW check failures caused by this bead (audit entries for _epic_follow_release path-passing sites; wire trailing-field test now expects wait_epic_follows, matching Rust order). 43/43 targeted tests pass (27 wait_epic_follow_release + 14 wire + 2 audit). sase-core: 174 agent_scan lib tests pass, clippy clean, bead Rust files rustfmt-clean. Pre-existing failures recorded as PROPOSED FOLLOW-UP (TUI import budget 3570==cap on clean base; sase-core fmt drift on untouched files). No epic-symbol leftovers.

[2026-10-07T15:20:05Z · sase-1h7.5--2] PROPOSED FOLLOW-UP: tests/ace/tui/test_app_import_budget.py fails at the exact boundary (module_count 3570 is not < _MAX_MODULE_COUNT 3570). Reproduces on the clean base (verified via git stash -u: base closure also measures 3570), so it is dependency/environment drift, not bead work. Options: bump _MAX_MODULE_COUNT with a measured justification or trim the TUI app import closure.

[2026-10-07T15:20:22Z · sase-1h7.5--2] PROPOSED FOLLOW-UP: just check lint (symvision) fails on private imports of _runs in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py. Neither file is touched by this bead; pre-existing. See symvision memory before fixing.

[2026-10-07T15:20:33Z · sase-1h7.5--2] PROPOSED FOLLOW-UP: sase-core check fails at the fmt stage on a clean tree (cargo fmt wants to rewrap vec! literals in crates/sase_macro_lsp/src/server/tests/completion.rs; toolchain cargo 1.98.1). No sase-core files were modified by this bead (DIRTY 0->0), so this is rustfmt-version drift at sase-core HEAD. Later check stages never ran.

[2026-10-07T15:20:51Z · sase-1h7.5--2] Verified: 27/27 tests/test_wait_epic_follow_release.py pass plus related audit/fallback suites (38 passed total); wire-order and path-passing audit tests updated for the new wait_epic_follows field and release helpers and now pass; just rust-install rebuilt the venv extension (exit 0). Joined sase check red only on pre-existing items: TUI import-budget boundary 3570 (reproduces on clean base, noted as follow-up), symvision private-import lint in untouched files (noted), one FLAKY discard-guard test. sase-core check red only at fmt on a clean tree (rustfmt drift, noted). No epic-symbol leftovers. Parent sase-1h7 left open.

[2026-10-07T16:07:03Z · bryanbugyi34@gmail.com] The last agent's commit got lost I think.

[2026-10-07T19:36:15Z · sase-1h7.5--3] PROPOSED FOLLOW-UP: sase-core check red on 1 stale test only: editor::directive contract (crates/sase_core/src/editor/directive/tests.rs:104) and sase_core_py surfaces.rs:690 expect wait keywords without for_epic, but committed grammar from closed sase-1h7.3 (21c539fd) adds for_epic. Fails identically on clean tree (verified via git stash in sase-core). Bead Rust files fmt/clippy clean; 21 wait_epic_follow + 171 agent_scan lib tests pass. --body -r Record pre-existing sase-core failure blocking full check green

[2026-10-07T19:36:30Z · sase-1h7.5--3] PROPOSED FOLLOW-UP: sase just-check scoped lane red on 5 items that reproduce identically on a clean tree (verified via git stash -u this turn): 3x tests/main/test_bead_fast_path.py, 1x test_finalizers_discard_guard_before_head.py foreign-race exempt, and the TUI import-budget boundary (3570 == cap 3570). This bead's own +4 import-closure regression (eager epic_follow_release imports) was fixed via lazy package __getattr__ + lazy kill-path imports; closure back to clean-base 3570. This bead also fixed 1 real failure: wait_blocking named-duration test needed the shared patch_index_updates helper to watch the new set_waiting_until publisher. --body -r Record pre-existing sase check failures verified on clean tree

[2026-10-07T19:36:44Z · sase-1h7.5--3] Release phase done: shared resolve_wait_release routes runner-initial, parked-fallback, AXE wait_checks chop, and kill/dismiss; FOLLOWING targets promote to pinned bead waits under directive-lock CAS; wait_epic_follows persisted; two-stage rewrite clobber fixed. Verified: 120/120 pass (11 release suites + wait_blocking), mypy/ruff/fmt clean on touched files, sase-core 21 wait_epic_follow + 171 agent_scan pass with fmt/clippy clean on bead Rust files, epic-symbols clean. Pre-existing reds (verified identical on clean trees, follow-up notes on bead): TUI import-budget boundary 3570, 3x bead_fast_path, 1x discard-guard, sase-core directive contract stale on for_epic. Parent sase-1h7 left open; sase-core-revision.txt untouched.

## Dependencies

- **Depends on:** [sase-1h7.3](sase-1h7.3.md) ✓ · ⧖ 2026-10-06
- **Depends on:** [sase-1h7.4](sase-1h7.4.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.6](sase-1h7.6.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.7](sase-1h7.7.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.5.md) | [sase-1h7.5](sase-1h7.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d742e20`](https://github.com/sase-org/sase-core/commit/d742e207c697249c75dd42fac669d338e4bbed0b) | feat(wait): wire wait\_epic\_follows scan fields and dismissed-member reducer fix (sase-1h7.5) | [sase-1h7.5](sase-1h7.5.md) | 2026-10-07 15:38:14 EDT |
| sase | [`333034a`](https://github.com/sase-org/sase/commit/333034a60aa09d6279d508b4d39f0ab9707da912) | feat(wait): route every release path through shared epic-follow release (sase-1h7.5) | [sase-1h7.5](sase-1h7.5.md) | 2026-10-07 16:26:49 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h7.5--3][1] | Finish bead sase-1h7.5 release implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.5.md

<!-- sase:referenced-by:end -->
