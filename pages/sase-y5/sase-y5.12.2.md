# Bead: sase-y5.12.2 — Fix the verbose reset label, baseline the pager flake, and finish docs

[Bead Pages](../README.md) / [sase-y5.12](sase-y5.12.md) / sase-y5.12.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-y5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-y5.land.md) · **Assignee:** `sase-y5.12.2` · **Size:** small
**Created:** 2026-09-09 06:11:33 EDT · **Closed:** 2026-09-09 07:38:42 EDT
**Plan:** [202609/usage\_context\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_context_recovery.md)

## Description

usage-release-residue: Fix the verbose reset label 0s-ago defect in shared usage presentation, add the sase-yq flake-baseline entry so the selection-health gate is green, and add the missing subscription-usage section to docs/agent_providers.md.

## Notes

[2026-09-09T11:38:08Z · sase-y5.12.2] PROPOSED FOLLOW-UP: tests/pager/test_syntax_activation.py imports tests.pager.test_app which is missing on this tree — ModuleNotFoundError during full-lane collection, unrelated to usage presentation.

[2026-09-09T11:38:42Z · sase-y5.12.2] Fixed timestamp_label so future resets omit the (0s ago) suffix (in 1h (2027-01-15 04:00:00 EST)); past observed_at still keeps relative age. Regression tests in tests/llm_provider/test_usage_presentation.py. Regenerated Providers · Usage PNG goldens at 120/80/60 after inspecting the 0s-ago-only diffs. Appended # sase-yq flake-baseline node; just selection-health --fail-on-new-flake exits 0. Added Subscription Usage section to docs/agent_providers.md. epic-symbols: none. just check lint gates passed; 156-file scoped selection 1763 passed; visual usage snapshots updated.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.12.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.12.2/README.md) | [sase-y5.12.2](sase-y5.12.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d165fbb`](https://github.com/sase-org/sase/commit/d165fbbaaf0abfac0a23114e4a25a5381715beb6) | fix(usage): omit relative age on future verbose reset labels | [sase-y5.12.2](sase-y5.12.2.md) | 2026-09-09 07:40:24 EDT |
