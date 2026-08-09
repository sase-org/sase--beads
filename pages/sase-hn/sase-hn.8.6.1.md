# Bead: sase-hn.8.6.1 — Unbreak the gate and reopen the test-tree work list

[Bead Pages](../README.md) / [sase-hn.8.6](sase-hn.8.6.md) / sase-hn.8.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hn.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.8.land/README.md) · **Assignee:** `sase-hn.8.6.1` · **Size:** medium
**Created:** 2026-08-09 04:14:54 EDT · **Closed:** 2026-08-09 04:43:30 EDT
**Plan:** [202608/patch\_audit\_gate\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_audit_gate_repair.md)

## Description

gate-repair: stop the lint gate from hard-failing on unmaterialized linked repos, restore the strict all-repos invocation for the explicit audit command, and add a temporary opt-in flag that re-enables content-aware tests/ and smoke/ classification so the sweep phases have an enforceable work list.

## Notes

[2026-08-09T08:43:30Z · sase-hn.8.6.1] Implemented gate repair: lint terminology gate now passes --allow-missing-linked-repos, explicit audit-patch-stitch-terminology runs the direct strict missing-repo command, and --strict-test-fixtures enables content-aware tests/smoke classification. Verified pytest tests/test_patch_stitch_terminology_audit.py; just _lint-patch-stitch-terminology and direct audit with --allow-missing-linked-repos exit 0 while reporting missing sase-github, sase-telegram, sase-nvim, chezmoi; just audit-patch-stitch-terminology exits 1 when those repos are missing; strict JSON audit exits 1 with 2953 defects: tests/ace/tui/** 2709, tests/test_revert.py 81, tests/ace/changespec/** 65, tests/test_archive.py 45, tests/ace/test_changespec_archive.py 25, tests/ace/deltas/** 18, everything else under tests/ 10, smoke/** 0; just lint passed; just check passed and escalated to full suite; just check-full passed.

[2026-08-09T08:44:47Z · sase-hn.8.6.1] Verified pytest tests/test_patch_stitch_terminology_audit.py, just _lint-patch-stitch-terminology, strict/default audit entry points, just lint, just check, and just check-full.

## Dependencies

- **Blocks:** [sase-hn.8.6.2](sase-hn.8.6.2.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-hn.8.6.3](sase-hn.8.6.3.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.8.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.8.6.1/README.md) | [sase-hn.8.6.1](sase-hn.8.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4a85503`](https://github.com/sase-org/sase/commit/4a855032ff96612934d810a9ac0fed463d2f7448) | fix: keep Patch terminology lint unblocked by missing repos | [sase-hn.8.6.1](sase-hn.8.6.1.md) | 2026-08-09 04:45:47 EDT |
