# Bead: sase-h8.10.5.1 — Replace the load-sensitive contract runtime oracle

[Bead Pages](../README.md) / [sase-h8.10.5](sase-h8.10.5.md) / sase-h8.10.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h8.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.land/README.md) · **Assignee:** `sase-h8.10.5.1` · **Size:** medium
**Created:** 2026-08-08 13:27:27 EDT · **Closed:** 2026-08-08 14:00:14 EDT
**Plan:** [202608/h8\_10\_remaining\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/h8_10_remaining_landing.md)

## Description

contract-budget: replace the still-load-sensitive normalized-child-CPU contract-set guard with the deterministic manifest-entry budget explicitly allowed by the original contract-set plan, remove the now-unused calibration machinery, and prove the guard and its diagnostic remain useful without any real-time or CPU-time correctness oracle.

## Notes

[2026-08-08T17:59:49Z · sase-h8.10.5.1] PROPOSED FOLLOW-UP: Flake baseline gate retains fixed XPrompt prompt-contract records - just check-full full pytest passed, but selection-health --fail-on-new-flake still reports historical tests/test_bead_xprompt_tags.py nodeids from earlier heads after the baseline; land should triage the baseline/store outcome before landing.

[2026-08-08T18:00:14Z · sase-h8.10.5.1] Replaced timed normalized-child-CPU contract runtime oracle with exact 35-entry manifest budget and diagnostic, removed normalization helper/tests, updated docs/comments, and fixed stale bd/work_task prompt assertion found during full-check verification. Verified .venv/bin/pytest -q tests/test_contract_manifest.py: 3 passed; SASE_CONTENTION_REPEAT=6 just test-contention -- tests/test_contract_manifest.py: 0 failed nodes across 6 repeats; XPrompt assertion node: passed; just check: passed after full-suite escalation. just check-full full pytest lane passed, then flake baseline gate failed on retained historical tests/test_bead_xprompt_tags.py records that predate this phase/currently pass or no longer exist; recorded PROPOSED FOLLOW-UP on this bead for land triage.

[2026-08-08T18:01:13Z · sase-h8.10.5.1] Verified manifest guard with serial pytest, six-repeat contention harness, just check, and just check-full full pytest lane; check-full remains blocked only by retained historical flake-baseline telemetry noted as proposed follow-up.

## Dependencies

- **Blocks:** [sase-h8.10.5.3](sase-h8.10.5.3.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.10.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.5.1/README.md) | [sase-h8.10.5.1](sase-h8.10.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`38fd25a`](https://github.com/sase-org/sase/commit/38fd25afdcda3481debf5324697ebf034eed62dd) | test: replace contract runtime oracle with manifest budget | [sase-h8.10.5.1](sase-h8.10.5.1.md) | 2026-08-08 14:02:05 EDT |
