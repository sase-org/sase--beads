# Bead: sase-ko.3 — Guard skips stop consuming run\_every cadence

[Bead Pages](../README.md) / [sase-ko](README.md) / sase-ko.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yx/README.md) · **Assignee:** `sase-ko.3` · **Size:** small
**Created:** 2026-08-12 16:00:14 EDT · **Closed:** 2026-08-12 16:12:51 EDT
**Plan:** [202608/chop\_agent\_runners\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202608/chop_agent_runners_guard.md)

## Description

guard-cadence: stop advancing a chop's `run_every` clock when the skip came from an `inhibit_if` guard rather than from the configured trigger, so a guarded chop retries on the next tick.

## Notes

[2026-08-12T20:12:51Z · sase-ko.3] Implemented: added ChopRunOutcome.advances_cadence (default True); record_preflight_outcome in chop_runner_policy.py sets it False only when status=skipped and preflight.decision.provider is not a trigger provider (always/git.commits_since); Lumberjack._outcome_to_result gates update_timestamp on outcome.advances_cadence in addition to run_every being set. Documented behavior change in docs/axe.md. Added two tests: guard skip does not advance cadence, git.commits_since trigger skip still advances cadence. Verified via 'just check' (all lint gates + scoped test lane, 193/2562 files) after 'just install' rebuilt the Rust core binding — all green, exit 0.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ko.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ko.3/README.md) | [sase-ko.3](sase-ko.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e5b0b5f`](https://github.com/sase-org/sase/commit/e5b0b5f5ca301def9941ac49f67b5f8a017ee899) | fix(axe): stop guard skips from consuming run\_every cadence | [sase-ko.3](sase-ko.3.md) | 2026-08-12 16:13:27 EDT |
