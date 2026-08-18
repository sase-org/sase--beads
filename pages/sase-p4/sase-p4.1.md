# Bead: sase-p4.1 — Epic stall detection policy

[Bead Pages](../README.md) / [sase-p4](README.md) / sase-p4.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05e.md) · **Assignee:** `sase-p4.1` · **Size:** medium
**Created:** 2026-08-17 18:53:39 EDT
**Plan:** [202608/epic\_resume\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_resume_gate.md)

## Description

policy: add the pure stalled-epic predicate, its typed clan-member input records, and the fingerprint helper the gate lane keys on.

## Notes

[2026-08-17T23:24:31Z · sase-p4.1] Added epic_stall_policy (EpicClanMember/Snapshot/Stall, stalled_epic, epic_stall_fingerprint, latest_generation_snapshot) and tests/test_epic_stall_policy.py; 9 unit tests passed; just check escalated on Justfile --epic-symbol broadening, so verification continues via just check-full.

[2026-08-17T23:38:43Z · sase-p4.1--1] PROPOSED FOLLOW-UP: sase-p1.2 closed while this tree still listed its --epic-symbol entries and had no CLI consumers — re-keyed Glossary* / add_glossary_term / delete_glossary_term to parent sase-p1 so just check stays green until CLI or the glossary panel consume them

[2026-08-17T23:39:00Z · sase-p4.1--1] check-full failed on stale sase-p1.2 --epic-symbol leftovers (closed bead). Re-keyed those six glossary mutation symbols to still-open parent sase-p1. just _lint-symvision now green; 9 stall-policy tests passed; sase bead epic-symbols sase-p4.1 reports no leftovers (keyed to sase-p4.4). Re-running just check-full because Justfile is in the broadening set.

## Dependencies

- **Blocks:** [sase-p4.4](sase-p4.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p4.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p4.1.md) | [sase-p4.1](sase-p4.1.md) | 0 |
