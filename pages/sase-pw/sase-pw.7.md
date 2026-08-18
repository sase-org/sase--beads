# Bead: sase-pw.7 — Agents-tab project scoping

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.7` · **Size:** medium
**Created:** 2026-08-18 11:30:35 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

agents: seed the Agents-tab search query with the current project behind the default-off `seed_agents_query` setting, and attribute a seeded scope visibly in the info panel.

## Notes

[2026-08-18T19:14:52Z · sase-pw.7] PROPOSED FOLLOW-UP: tests/feature_flags/test_integrity.py::test_kind_mismatch_when_default_disagrees_with_kind is broken on HEAD — demo_flag() no longer accepts default= after c5a0dcf4a (flag default now comes from kind). Unrelated to Agents-tab seeding; just check hits it only when the suite escalates (Justfile is in the broadening set because this phase consumed resolve_current_project / CurrentProject and dropped those stale --epic-symbol entries).

[2026-08-18T19:15:10Z · sase-pw.7] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py (test_checked_in_snapshot_has_no_drift, test_current_structural_view_matches_checked_in_snapshot) fail with dict key-order drift against the argparse tree; no CLI in this phase. Same full-suite escalation as the flag integrity test.

## Dependencies

- **Depends on:** [sase-pw.1](sase-pw.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.3](sase-pw.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.9](sase-pw.9.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.7.md) | [sase-pw.7](sase-pw.7.md) | 0 |
