# Bead: sase-191.3 — Run and hand-audit the DoD-5 backtest, then close sase-18j.5

[Bead Pages](../README.md) / [sase-191](README.md) / sase-191.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rz](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rz.md) · **Assignee:** `sase-191.3` · **Size:** medium
**Created:** 2026-09-25 07:43:32 EDT · **Closed:** 2026-09-25 10:11:51 EDT
**Plan:** [202609/e3\_precision\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202609/e3_precision_gate.md)

## Description

precision-gate: run the repaired backtest on athena, hand-audit at least 50 KNOWN labels, tighten the knobs only if the audit fails, record the evidence and follow-ups, and close sase-18j.5 so the queued E3 phases resume.

## Notes

[2026-09-25T14:01:41Z · sase-191.3] PROPOSED FOLLOW-UP: sase-core owner-matching rule change under a new rule version (token stoplist or path-level match for match_owners/locator_tokens in crates/sase_core/src/tool_run/triage/classify.rs), plus a pin move past it. Evidence: precision-gate probe classified a KNOWN fixture at src/sase/tool/executor.py against 319 live candidates and matched unrelated beads sase-106 and sase-10a; DISCOVERED ISSUE notes appended to sase-18j and sase-18j.6. Needed before sase-18j.6 renders owners. -r phase 5 plan owner-matching follow-up

[2026-09-25T14:11:51Z · sase-191.3] Precision gate passed round 1 (seed 7, default knobs): backtest over 578 runs, 60/60 sampled KNOWN + 17/17 KNOWN-but-touched hand-audited pre-existing (100%), added-file count 0; artifacts file:explicit:ef446cbbb5df4283a4022132 + file:explicit:a6279075b0c1d3b4e652949c on sase-18j.5. Owner-matching over-match confirmed via read-only classify probe (executor.py fixture matched sase-106/sase-10a); DISCOVERED ISSUE notes on sase-18j + sase-18j.6, PROPOSED FOLLOW-UP on this bead. Verified: sase tool run check green (exit 0), epic-symbols empty for sase-191.3 and sase-18j.5, sase-18j.5 closed, sase-18j.6 dependency released (runners still alive, no bead work run). No repo files changed.

## Dependencies

- **Depends on:** [sase-191.1](sase-191.1.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-191.2](sase-191.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-191.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.3/README.md) | [sase-191.3](sase-191.3.md) | 0 |
