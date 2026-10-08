# Bead: sase-1h8.13.1.2 — Run every mutation suite in cached and replay modes

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.2` · **Size:** medium
**Created:** 2026-10-08 14:46:04 EDT · **Closed:** 2026-10-08 17:21:27 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

## Description

dual-mode-tests: add fixture support so the existing mutation suites run against a git-backed cached store and a plain replay store without macro_rules, check cache-equals-replay after cached-mode tests, split over-cap test files, and fix any parity defects the cached runs expose in the already-cached create/note/update paths.

## Notes

[2026-10-08T21:21:27Z · sase-1h8.13.1.2] dual-mode-tests done in linked sase-core (uncommitted): new StoreMode fixture + assert_cache_equals_replay/assert_no_full_replay in mutation/tests/support.rs, new mutation/tests/dual_mode.rs with 10 cached+replay tests covering create, note append/update (zero full replays), note edit/remove, close/open, remove cascade, claims, dependencies/references, links, plus-one/snooze, ready marking. No parity defects exposed in cached create/note/update paths, no assertions weakened, notes_update.rs untouched (no split needed). Verified: just fmt, just fast, bead::mutation 185 pass, bead::read_model 20 pass, bead_read/event/read_model parity suites pass (35+6+16), sase_core_py 296 pass, sase tool run check exit 0. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1h8.13.1.1](sase-1h8.13.1.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.3](sase-1h8.13.1.3.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.2/README.md) | [sase-1h8.13.1.2](sase-1h8.13.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@906570e`](https://github.com/sase-org/sase-core/commit/906570e8afae29ff1efe283f18c45bcc05853c53) | test(bead-mutation): add mode-parameterized dual-mode parity fixtures | [sase-1h8.13.1.2](sase-1h8.13.1.2.md) | 2026-10-08 17:23:27 EDT |
