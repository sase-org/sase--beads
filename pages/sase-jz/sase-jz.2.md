# Bead: sase-jz.2 — Replace ci\_watch fix proposals with LaunchApproval gates

[Bead Pages](../README.md) / [sase-jz](README.md) / sase-jz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yi](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yi/README.md) · **Assignee:** `sase-jz.2` · **Size:** medium
**Created:** 2026-08-12 10:38:59 EDT · **Closed:** 2026-08-12 11:16:46 EDT
**Plan:** [202608/retire\_audit\_chops\_and\_gate\_ci\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_audit_chops_and_gate_ci_fixes.md)

## Description

gate_ci_fix: stop emitting `proposed_launches` from `bugyi_chop_ci_watch` and instead create one durable LaunchApproval gate per mature red CI failure, with a self-sufficient prompt, a version-2 fix ledger recording each gate's request id, and layered suppression that makes a duplicate gate impossible; update the report, tests, and README to match.

## Notes

[2026-08-12T15:16:46Z · sase-jz.2] Phase 2 already committed and published as e1dadf0 (feat(ci-watch)!: gate CI-fix launches behind LaunchApproval instead of proposing them) in gh:bbugyi200/bugyi-chops, 0 ahead/0 behind origin/master. Independently re-verified at HEAD: just check passes clean (ruff format/check, mypy, 162 tests/91% coverage, build+twine). ci_watch.py now files one durable LaunchApproval gate per mature red failure via LaunchGateClient instead of emitting proposed_launches, backed by a v2 fix ledger and layered suppression order; README and tests updated to match.

## Dependencies

- **Depends on:** [sase-jz.1](sase-jz.1.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-jz.3](sase-jz.3.md) ✓ · ⧖ 2026-08-12
