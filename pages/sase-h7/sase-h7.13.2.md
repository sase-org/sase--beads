# Bead: sase-h7.13.2 — Repair sase-telegram against the custom-gate presentation contract

[Bead Pages](../README.md) / [sase-h7.13](sase-h7.13.md) / sase-h7.13.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.land/README.md) · **Assignee:** `sase-h7.13.2` · **Size:** small
**Created:** 2026-08-07 23:12:17 EDT · **Closed:** 2026-08-07 23:21:29 EDT
**Plan:** [202608/gate\_inputs\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_inputs_landing.md)

## Description

telegram-presentation: give sase-telegram's custom-gate test specs the `presentation.title` this epic began requiring, and audit that repo for any other spec the same validation now rejects.

## Notes

[2026-08-08T03:21:07Z · sase-h7.13.2] PROPOSED FOLLOW-UP: sase-telegram has 3 tests failing against sase==0.16.0 (PyPI), unrelated to this epic — tests/test_custom_gates.py::test_task_triage_outbound_renders_tracks_attaches_and_launches and ::test_registry_declared_generic_forms_render_keyboards expect keyboards/kinds from before bead-snooze support shipped (missing Snooze/Snooze-with-feedback buttons, KeyError on registered_gate_kinds() including "bead_snooze"), and ::test_launch_approval_uses_the_same_singleton_renderer expects a generic "Send Feedback" button where sase now renders "Reject with feedback". sase-telegram formatting/tests need to catch up with already-released sase gate button/kind changes.

[2026-08-08T03:21:29Z · sase-h7.13.2] Fixed sase-telegram: added presentation.title to tests/test_custom_gates.py::_custom_spec() (the only custom-gate spec builder missing it; _inputs_gate_spec already had title/icon/notes). Audited the whole repo for kind==custom literals and presentation dicts (grep for "kind": and presentation"; no other custom spec is missing icon or notes. Verified sase's build_task_triage_gate_spec needs no change: kind is task_triage (not custom) and it already sets title via bounded_gate_title. Verification in sase-telegram (afa933b) with this workspace's sase overlaid per uv pip install --no-deps -e: before the fix, 10 failed/544 passed with 7 distinct tests failing on 'custom gates require presentation.title' (not the 9 the epic bead recorded from a stashed tree) plus 3 unrelated pre-existing failures; after the fix, those 7 pass and only the 3 pre-existing failures remain (confirmed they also fail against released PyPI sase==0.16.0, so unrelated to this epic — recorded as PROPOSED FOLLOW-UP). ruff and mypy both clean. NOTE: the sase-telegram fix is an uncommitted working-tree diff in the linked-repo workspace checkout (repos/linked/sase-telegram/tests/test_custom_gates.py) — not committed, per the no-commit-without-explicit-request rule.

[2026-08-08T03:22:07Z · sase-h7.13.2] Fixed missing presentation.title in sase-telegram's _custom_spec() test fixture (tests/test_custom_gates.py); audited repo for other custom-kind specs missing title/icon/notes (none found); verified build_task_triage_gate_spec needs no change (kind=task_triage, already sets title). Verified with workspace sase overlaid into sase-telegram venv: 10 failed/544 passed -> 3 failed/551 passed; 3 remaining failures are pre-existing, unrelated, and reproduce against released PyPI sase==0.16.0. ruff and mypy clean.

[2026-08-08T03:22:24Z · sase-h7.13.2] verification recheck

## Dependencies

- **Blocks:** [sase-h7.13.5](sase-h7.13.5.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.13.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.13.2/README.md) | [sase-h7.13.2](sase-h7.13.2.md) | 0 |
