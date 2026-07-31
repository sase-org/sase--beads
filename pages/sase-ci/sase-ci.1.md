# Bead: sase-ci.1 — Adapter-owned gate capabilities and in-repo adoption

[Bead Pages](../README.md) / [sase-ci](README.md) / sase-ci.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qh/README.md) · **Assignee:** `sase-ci.1` · **Size:** medium
**Created:** 2026-07-31 16:13:15 UTC · **Closed:** 2026-07-31 16:26:39 UTC
**Plan:** [202607/telegram\_generic\_gate\_support.md](https://github.com/sase-org/sase--plans/blob/main/202607/telegram_generic_gate_support.md)

## Description

core-registry: add default_feedback, generic_form, and branch_actionable to GateAdapter, collapse the duplicated `kind == "custom"` feedback derivations onto the adapter, and replace ACE's hardcoded gate-action and gate-kind literals with registry lookups.

## Notes

[2026-07-31T16:23:06Z · sase-ci.1] PROPOSED FOLLOW-UP: Regenerate stale sase_beads provider skills — `sase validate` reports five generated provider skill files are out of date in chezmoi.

[2026-07-31T16:23:15Z · sase-ci.1] PROPOSED FOLLOW-UP: Repair telegram generic-gate plan links — `sase validate` reports the epic plan and prompt are missing their bidirectional prompt links.

[2026-07-31T16:26:39Z · sase-ci.1] Verified after just install: focused gate/ACE regressions passed (41 tests); full just test passed (24,920 passed, 7 skipped); just check passed Python/Markdown formatting, keep-sorted, Ruff, mypy, pyscripts, changelog, Symvision, and toobig before unrelated stale-provider-skill and plan-link SASE validation failures recorded as PROPOSED FOLLOW-UP notes. git diff --check is clean.

[2026-07-31T16:27:27Z · sase-ci.1] Verified focused notification-gate coverage (41 passed), full pytest (24,920 passed, 7 skipped), and formatting, Ruff, mypy, Symvision, script/changelog, and size checks; unrelated stale generated skill and plan-link metadata validations were recorded as proposed follow-ups.

## Dependencies

- **Blocks:** [sase-ci.2](sase-ci.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ci.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ci.1/README.md) | [sase-ci.1](sase-ci.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`6e5b360`](https://github.com/sase-org/sase/commit/6e5b36028a879f2f86d2678d7d07dde30970ebef) | feat: derive gate behavior from adapter capabilities | [sase-ci.1](sase-ci.1.md) | 2026-07-31 16:28:17 |
