# Bead: sase-rj.3 — Complete responsive directive support in the ACE prompt widget

[Bead Pages](../README.md) / [sase-rj](README.md) / sase-rj.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08s](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08s.md) · **Assignee:** `sase-rj.3` · **Size:** medium
**Created:** 2026-08-20 13:44:20 EDT
**Plan:** [202608/xprompt\_directive\_completion\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_directive_completion_parity.md)

## Description

prompt-widget: replace the prompt widget's private directive tables and token classifier with the shared contract, wire warm dynamic catalogs for bead, identity, model, and path values, and preserve the non-blocking completion path.

## Notes

[2026-08-20T19:20:17Z · sase-rj.3] PROPOSED FOLLOW-UP: flake — tests/main/test_completion_candidates_contract.py::test_candidates_fast_path_wall_clock_budget[flag] failed at 800ms vs 450ms CI budget during an escalated just check, then passed serially in 160ms; the test file itself calls the wall-clock check inherently flaky.

[2026-08-20T19:20:49Z · sase-rj.3] PROPOSED FOLLOW-UP: landing depends on an unpublished sase-core-rs — just check core-floor-probe reports directive_contract, directive_completion_context, and directive_completion_candidates first appear in sase-core 04c27f2 with no release tag yet; local just install builds the linked checkout, but published 0.29.5 cannot serve ACE adapters until a core release includes those bindings.

## Dependencies

- **Depends on:** [sase-rj.1](sase-rj.1.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rj.4](sase-rj.4.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rj.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rj.3.md) | [sase-rj.3](sase-rj.3.md) | 0 |
