# Bead: sase-p4.1 — Epic stall detection policy

[Bead Pages](../README.md) / [sase-p4](README.md) / sase-p4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05e.md) · **Assignee:** `sase-p4.1` · **Size:** medium
**Created:** 2026-08-17 18:53:39 EDT · **Closed:** 2026-08-17 20:59:36 EDT
**Plan:** [202608/epic\_resume\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_resume_gate.md)

## Description

policy: add the pure stalled-epic predicate, its typed clan-member input records, and the fingerprint helper the gate lane keys on.

## Notes

[2026-08-17T23:24:31Z · sase-p4.1] Added epic_stall_policy (EpicClanMember/Snapshot/Stall, stalled_epic, epic_stall_fingerprint, latest_generation_snapshot) and tests/test_epic_stall_policy.py; 9 unit tests passed; just check escalated on Justfile --epic-symbol broadening, so verification continues via just check-full.

[2026-08-17T23:38:43Z · sase-p4.1--1] PROPOSED FOLLOW-UP: sase-p1.2 closed while this tree still listed its --epic-symbol entries and had no CLI consumers — re-keyed Glossary* / add_glossary_term / delete_glossary_term to parent sase-p1 so just check stays green until CLI or the glossary panel consume them

[2026-08-17T23:39:00Z · sase-p4.1--1] check-full failed on stale sase-p1.2 --epic-symbol leftovers (closed bead). Re-keyed those six glossary mutation symbols to still-open parent sase-p1. just _lint-symvision now green; 9 stall-policy tests passed; sase bead epic-symbols sase-p4.1 reports no leftovers (keyed to sase-p4.4). Re-running just check-full because Justfile is in the broadening set.

[2026-08-18T00:59:18Z · sase-p4.1--2] PROPOSED FOLLOW-UP: just check-full test-cost budget gate failed after 32572 passed / 13 skipped — peak_worker_rss_kib 1405040 and ACE/parser/subprocess/textual causes over 20% CI tolerance; all 8 recent host recordings miss the same RSS budget and node count grew ~28.4k→~32.5k since the 2026-08-10 calibration. Corroborates in-progress sase-j0, not caused by the unused stall-policy module. Do not raise limits to hide this.

[2026-08-18T00:59:36Z · sase-p4.1--2] Epic stall policy landed: src/sase/bead/epic_stall_policy.py (EpicClanMember/Snapshot/Stall, stalled_epic, epic_stall_fingerprint, latest_generation_snapshot) and tests/test_epic_stall_policy.py. Verified: 9 unit tests passed; ruff/mypy/symvision green; sase bead epic-symbols sase-p4.1 reports no leftovers (six public symbols keyed to still-open sase-p4.4). just check-full ran 32572 passed / 13 skipped and every lint gate including symvision; it failed only tools/check_test_cost_budgets (RSS + ACE/parser/subprocess/textual causes), which matches in-progress sase-j0 and is recorded as a PROPOSED FOLLOW-UP. Stale sase-p1.2 --epic-symbol leftovers were re-keyed to still-open parent sase-p1.

[2026-08-18T01:01:17Z · sase-p4.1--2] Verified the shared stall predicate: 9 tests for plain stall, live member, closed epic, settle window, killed/stopped, failed land agent, fingerprint stability/change, and newest generation. ruff, mypy, and just _lint-symvision passed. just check-full ran 32572 passed / 13 skipped and every lint gate including symvision; the only failure was just test-cost (peak_worker_rss_kib plus ACE/parser/subprocess/textual causes), already tracked as in-progress sase-j0 and recorded as PROPOSED FOLLOW-UP. Justfile --epic-symbol leftovers for this phase are keyed to still-open sase-p4.4; sase bead epic-symbols sase-p4.1 reported none. Stale sase-p1.2 leftovers re-keyed to still-open parent sase-p1.

## Dependencies

- **Blocks:** [sase-p4.4](sase-p4.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p4.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p4.1.md) | [sase-p4.1](sase-p4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`567605a`](https://github.com/sase-org/sase/commit/567605a8fba6c157337d689c6f862be025f642ab) | feat(bead): add shared epic stall detection policy | [sase-p4.1](sase-p4.1.md) | 2026-08-17 21:03:00 EDT |
