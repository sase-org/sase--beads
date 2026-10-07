# Bead: sase-1h7.4 — Epic-follow reducer and fact collector

[Bead Pages](../README.md) / [sase-1h7](README.md) / sase-1h7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3v.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3v.linker.w0.md) · **Assignee:** `sase-1h7.4` · **Size:** medium
**Created:** 2026-10-06 18:17:38 EDT · **Closed:** 2026-10-06 22:56:24 EDT
**Plan:** [202610/wait\_for\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_for_epic.md)

## Description

reducer: add the pure sase-core reducer that maps per-member facts to AGENT/NONE/LAUNCHING/FOLLOWING/BLOCKED with the deadlock guard and the cycle hook, bind it to Python, and add the Python fact collector over the wait-dependency index. Nothing is wired into release paths yet.

## Notes

[2026-10-07T02:02:38Z · sase-1h7.4] PROPOSED FOLLOW-UP: test_identity_and_hood_waits_defer_on_stale_membership fails identically on the clean base tree (hood_confirmation.confirmed is True, expected False); unrelated to the reducer phase

[2026-10-07T02:50:23Z · sase-1h7.4--1] PROPOSED FOLLOW-UP: just check scoped run had 2 unrelated flakes (test_muse_usage_probe_missed_mint_is_a_timeout_not_absence, test_mutation_completion_after_unmount_invalidates_memo); both pass in isolation, neither references wait/epic-follow code

[2026-10-07T02:55:21Z · sase-1h7.4--1] PROPOSED FOLLOW-UP: sase-core check fails on pre-existing rustfmt drift in bead/fingerprint.rs and beads/fingerprint.rs (untouched by this phase; phase files are rustfmt-clean)

[2026-10-07T02:56:24Z · sase-1h7.4--1] Verified: 18 Rust reducer tests + binding round-trip pass; 10 collector tests pass; sase check green except 2 unrelated flakes (pass in isolation); sase-core rustfmt drift pre-existing in untouched fingerprint files. sase-core-revision.txt not moved (needs sase-core commit hash; land agent work).

## Dependencies

- **Depends on:** [sase-1h7.1](sase-1h7.1.md) ✓ · ⧖ 2026-10-06
- **Blocks:** [sase-1h7.5](sase-1h7.5.md) ◐ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h7.4.md) | [sase-1h7.4](sase-1h7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4b4a052`](https://github.com/sase-org/sase-core/commit/4b4a0527c3c604b09dea759d3f6e3b4a23300e9e) | feat(wait): add pure wait\_epic\_follow reducer with Python binding (sase-1h7.4) | [sase-1h7.4](sase-1h7.4.md) | 2026-10-06 22:57:12 EDT |
