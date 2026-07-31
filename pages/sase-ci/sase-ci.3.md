# Bead: sase-ci.3 — Optional-feedback affordance for Telegram gate branches

[Bead Pages](../README.md) / [sase-ci](README.md) / sase-ci.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qh/README.md) · **Assignee:** `sase-ci.3` · **Size:** small
**Created:** 2026-07-31 16:13:23 UTC · **Closed:** 2026-07-31 16:46:02 UTC
**Plan:** [202607/telegram\_generic\_gate\_support.md](https://github.com/sase-org/sase--plans/blob/main/202607/telegram_generic_gate_support.md)

## Description

telegram-optional-feedback: add an `f<branch>` callback and per-branch feedback button so Telegram can attach optional feedback to a gate selection, matching the ACE gate form.

## Notes

[2026-07-31T16:45:47Z · sase-ci.3] PROPOSED FOLLOW-UP: sase-telegram just install leaves the stale PyPI sase 0.14.0 in .venv, so tests importing new sase modules (e.g. sase.bead.task_gate) fail to collect locally — make the Justfile _setup/install install sase from the local source checkout the way .github/workflows/ci.yml does.

[2026-07-31T16:46:02Z · sase-ci.3] Added the optional-feedback affordance in sase-telegram. render_gate_keyboard() now emits an f<branch> button (💬 <label> with feedback) for a singleton branch whose option declares feedback: optional (own row beneath it) and beside the submit control of an expanded AND branch whose current selection resolves to optional; disabled and required branches get none. _handle_gate_callback() gained an explicit f-prefix arm before the s-submit else, resolving the branch, computing the same selected_option_ids the primary control would submit, rejecting a disabled-feedback branch, and delegating to the existing _begin_gate_feedback()/process_text_message() path — no resolution-side change. feedback_is_command_input() stays in the path. Verified with just check in the sase-telegram checkout: ruff + mypy clean, 511 tests pass. New tests: TaskTriage launch via f0 records feedback while a plain c0 tap still resolves with none; f0 on an expanded custom AND group submits the toggled selection with feedback; a disabled-feedback branch renders no f button and its callback is refused; keyboard-shape assertions across all three feedback modes plus selection-tracking on an expanded group. Updated the two pre-existing keyboard-layout assertions for the new rows, and docs/inbound.md + docs/outbound.md. Deviation: the plan named tests/test_formatting.py for the keyboard-shape assertions; they went into tests/test_gate_flow.py, which already owns the render_gate_keyboard harness (_view/_option/_group) — test_formatting.py has none. No sase-repo changes.

[2026-07-31T16:46:31Z · sase-ci.3] Implemented optional-feedback gate button in sase-telegram: render_gate_keyboard emits f<branch_index> button for feedback_mode=optional branches (singleton row + expanded AND submit row); _handle_gate_callback gained an f-prefix arm that resolves the branch, computes selected_option_ids, refuses disabled-feedback branches, and delegates to _begin_gate_feedback. Docs updated. Verified with just check in the sase-telegram checkout: ruff + mypy clean, 511 tests passed, including new coverage for optional-vs-none resolution, expanded AND group submit with feedback, disabled-feedback refusal, and keyboard shapes across all three feedback modes.

## Dependencies

- **Depends on:** [sase-ci.2](sase-ci.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ci.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ci.3/README.md) | [sase-ci.3](sase-ci.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@0e73e3a`](https://github.com/sase-org/sase-telegram/commit/0e73e3a926605a94a60a74b0ed4d1b85dfcee5f1) | feat: add optional-feedback button to Telegram gate keyboards | [sase-ci.3](sase-ci.3.md) | 2026-07-31 16:47:00 |
